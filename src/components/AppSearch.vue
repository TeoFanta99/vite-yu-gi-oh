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
        <select v-model="store.archParam" @change="$emit('filter')">
            <option value="" selected>Seleziona un valore</option>
            <option v-for="(type, i) in store.archList" :key="i" :value="type.archetype_name">{{ type.archetype_name }}
            </option>
        </select>
    </form>
</template>

<style lang="scss"></style>
