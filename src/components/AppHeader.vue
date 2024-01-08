<script>
export default {
    name: "AppHeader",
}
</script>

<template>
    <header>
        <img src="../assets/img/logo yu gi oh.webp" alt="">
        <h1>Yu Gi Oh API</h1>
    </header>
</template>

<style lang="scss">
header {
    min-height: 80px;
    background-color: green;
    display: flex;
    align-items: center;
    padding-left: 10px;

    img {
        max-height: 40px;
    }
}
</style>
