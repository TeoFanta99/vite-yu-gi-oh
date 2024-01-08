<script>

export default {
    name: "AppCard",
}
</script>

<template>
    <div class="card">
        <img src="#" alt="img">
        <h4>nome della card</h4>
        <div>categoria</div>
    </div>
</template>

<style lang="scss">
.card {
    min-height: 100px;
    width: calc((100% / 5) - 5px);
    background-color: orange;
}
</style>
