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

      // chiamata API per i characters
      axios
        .get(myURL)
        .then((res => {
          console.log(res.data.data);
          store.charactersList = res.data.data;
        }))
        .catch((err) => {
          console.log("errori", err);
        })


      // chiamata API per gli archetype
      axios
        .get(myArchURL)
        .then((res => {
          console.log(res.data);
          store.archList = res.data;
        }))
        .catch((err) => {
          console.log("errori", err);
        })

      // filtrare le cards in base all'archetipo 
      if (store.archParam !== "") {

        // verifico se contiene o meno dei parametri
        if (myURL.includes('?')) {
          myURL += `&archetype=${store.archParam}`;
        } else {
          myURL += `?archetype=${store.archParam}`;
        }
      }

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
    <AppSearch @filter="filterArchetype" />
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
