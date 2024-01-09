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
      axios
        // ricevi dati da...
        .get(store.apiURL)

        // ... e stampali in pagina
        .then((res => {
          console.log(res.data.data);
          store.charactersList = res.data.data;
        }))
        .catch((err) => {
          console.log("errori", err);
        })
    }
  },
  created() {
    this.getCharacters();
  }
}
</script>

<template>
  <AppHeader />
  <main>
    <AppSearch />
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
