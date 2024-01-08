<script>
// importo components
import AppHeader from './components/AppHeader.vue'
import CardContainer from './components/CardContainer.vue'

// importo axios
import axios from 'axios';

// importo store
import { store } from './store';

export default {
  components: {
    AppHeader,
    CardContainer,
  },
  data() {
    return {
      store,
    }
  },
  methods: {
    getCharacters() {
      axios
        .get(store.apiURL)
        .then((res => {
          console.log(res.data);
          store.charactersList = res.data;
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
  display: flex;
  justify-content: center;
}
</style>
