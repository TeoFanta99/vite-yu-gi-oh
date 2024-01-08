<script>
import AppHeader from './components/AppHeader.vue'
import CardContainer from './components/CardContainer.vue'
import AppCard from './components/AppCard.vue'

export default {
  components: {
    AppHeader,
    CardContainer,
    AppCard
  }
}
</script>

<template>
  <AppHeader />
  <CardContainer />
  <AppCard />
</template>

<style lang="scss">
@use './styles/partials/variables' as *;
@use './styles/general.scss' as *;
</style>
