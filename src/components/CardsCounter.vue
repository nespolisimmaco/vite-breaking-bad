<script>
import { store } from '../store';
export default {
    name: "CardsCounter",
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <div class="counter">
        Numero di carte trovate: {{ store.cards.length }}
    </div>
</template>

<style scoped lang="scss">
@use "../style/partials/variables" as *;

.counter {
    background-color: $background;
    color: white;
    padding: 10px 1rem;
}
</style>