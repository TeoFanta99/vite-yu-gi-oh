<script>
import AppCard from './AppCard.vue'

export default {
    components: AppCard,
    name: "CardContainer",
}
</script>

<template>
    <div class="container">
        <div class="result"></div>
        <AppCard />
    </div>
</template>

<style>
.container {
    background-color: white;
    width: 80%;
    min-height: 300px;
    padding: 20px;

    .result {
        background-color: #212529;
        min-height: 40px;
    }
}
</style>
