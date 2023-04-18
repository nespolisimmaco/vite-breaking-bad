<script>
import { store } from "../store";
export default {
    name: "SelectArchetype",
    data() {
        return {
            store,
            archetypeOptions: ["Alien", "Ally of Justice", "Ancient Gear"]
        }
    }
}
</script>

<template>
    <div class="container">
        <select class="rounded py-1 px-3 border-0 mt-3" name="type" id="card-type" v-model="store.selectedArchetype"
            @change="$emit('filter')">
            <option value="">All</option>
            <option :value="archetype" v-for="archetype in archetypeOptions">{{ archetype }}</option>
        </select>
    </div>
</template>

<style scoped>
select {
    cursor: pointer;
}
</style>