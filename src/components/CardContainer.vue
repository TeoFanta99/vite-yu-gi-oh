<script>
import AppCard from './AppCard.vue'

export default {
    name: "CardContainer",
    components: {
        AppCard
    }
}
</script>

<template>
    <div class="container">
        <div class="result"></div>
        <div class="row">
            <AppCard />
            <AppCard />
            <AppCard />
            <AppCard />
            <AppCard />
        </div>

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

    .row {
        display: flex;
        flex-wrap: wrap;
        gap: 5px;
    }
}
</style>
