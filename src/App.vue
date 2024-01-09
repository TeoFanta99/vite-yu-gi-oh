<script>
// importo components
import AppHeader from './components/AppHeader.vue'
import CardContainer from './components/CardContainer.vue'
import AppSearch from './components/AppSearch.vue'

// importo axios
import axios from 'axios';

// importo store
import { store } from './store';

export default {
  components: {
    AppHeader,
    CardContainer,
    AppSearch
  },
  data() {
    return {
      store,
    }
  },
  methods: {
    getCharacters() {
      let myURL = store.apiURL;
      let myArchURL = store.optionApiURL;

      if (store.searchText !== '') {
        if (myURL.includes('?')) {
          // se l'URL già contiene ?, aggiungo & e il nuovo parametro
          myURL += `&${store.archParam}=${store.searchText}`;
        } else {
          // Se l'URL non contiene ancora parametri, aggiungi ? seguito dal nuovo parametro
          myURL += `?${store.archParam}=${store.searchText}`;
        }

      }

      // chiamata API per i characters
      axios
        // ricevi dati da...
        .get(myURL)

        // ... e stampali in pagina
        .then((res => {
          console.log(res.data.data);
          store.charactersList = res.data.data;
        }))
        .catch((err) => {
          console.log("errori", err);
        })



      // chiamata API per gli archetype
      axios
        // ricevi dati da...
        .get(myArchURL)

        // ... e stampali in pagina
        .then((res => {
          console.log(res.data);
          store.archList = res.data;
        }))
        .catch((err) => {
          console.log("errori", err);
        })


    },
  },
  created() {
    this.getCharacters();
  }
}
</script>

<template>
  <AppHeader />
  <main>
    <AppSearch @filter="getCharacters" />
    <CardContainer />
  </main>
</template>

<style lang="scss">
@use './styles/partials/variables' as *;
@use './styles/general.scss' as *;

main {
  background-color: orange;
  padding: 20px;
  width: 100%;
  min-height: 700px;
}
</style>
