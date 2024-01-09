<script>
import AppCard from './AppCard.vue'

import { store } from '../store';

export default {
    name: "CardContainer",
    components: {
        AppCard,
    },
    data() {
        return {
            store,
        }
    }
}
</script>

<template>
    <div class="container">
        <div class="result"></div>
        <div class="row">
            <!-- elemento da iterare -->
            <AppCard v-for="character in store.charactersList" :info="character" />
        </div>

    </div>
</template>

<style>
.container {
    background-color: white;
    width: 80%;
    min-height: 300px;
    padding: 20px;
    margin: 20px auto;

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
