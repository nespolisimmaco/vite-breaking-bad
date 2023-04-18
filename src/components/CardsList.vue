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
    <h2 class="loading" v-if="store.loading">Loading...</h2>
    <div class="container" v-else>
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

.loading {
    color: white;
}

.wrapper {
    background-color: $header-color;
}
</style>