<script>
import { store } from '../store'

export default {
    name: "AppSearch",
    data() {
        return {
            store,
        }
    }
}
</script>

<template>
    <form action="">
        <label for="types"></label>
        <select name="types" id="types">
            <option disabled value="">Seleziona un valore</option>
            <option value="valore 1">1</option>
            <option value="valore 2">2</option>
            <option value="valore 3">3</option>
        </select>
    </form>
</template>

<style lang="scss"></style>
