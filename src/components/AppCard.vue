<script>

export default {
    name: "AppCard",
    props: {
        info: Object
    }
}
</script>

<template>
    <div class="card">
        <img :src="info.card_images[0].image_url" alt="img">
        <h4>{{ info.name }}</h4>
        <div>{{ info.archetype }}</div>
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
