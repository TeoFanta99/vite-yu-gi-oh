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
        <select v-model="store.optionsList" @change="$emit('filter')">
            <option value="" selected>Seleziona un valore</option>
            <option v-for="(type, i) in store.archList" :key="i" :value="archetype">{{ type.archetype_name }}</option>
        </select>
    </form>
</template>

<style lang="scss"></style>
