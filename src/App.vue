<script>
import AppHeader from './components/AppHeader.vue'
import CardContainer from './components/CardContainer.vue'

export default {
  components: {
    AppHeader,
    CardContainer,
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
