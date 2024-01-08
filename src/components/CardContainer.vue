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
        <div class="row">
            <div class="col-6 col-md-4 col-lg-3 mb-5">
                <AppCard />
            </div>
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
}
</style>
