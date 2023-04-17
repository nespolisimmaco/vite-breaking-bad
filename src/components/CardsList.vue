<script>
import Card from "../components/Card.vue";
import { store } from '../store';

export default {
    name: "CardsList",
    components: {
        Card
    },
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <div class="container">
        <select class="rounded py-1 px-3 border-0 mt-3" name="type" id="card-type">
            <option value="alien">Alien</option>
        </select>

        <div class="wrapper mt-4 p-4">
            <div class="container-fluid">
                <div class="row row-cols-5 g-3">
                    <div class="col" v-for="card in store.cards" :key="card.id">
                        <Card :card="card" />
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">
@use "../style/partials/variables" as *;

.wrapper {
    background-color: $header-color;
}
</style>