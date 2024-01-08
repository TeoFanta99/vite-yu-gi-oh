<script>

export default {
    name: "AppCard",
}
</script>

<template>
    <div class="card">
        <img src="https://images.ygoprodeck.com/images/cards/34541863.jpg" alt="img">
        <h4>nome della card</h4>
        <div>categoria</div>
    </div>
</template>

<style lang="scss">
.card {
    min-height: 100px;
    width: calc((100% / 5) - 5px);
    background-color: orange;

    img {
        width: 100%;
    }
}
</style>
