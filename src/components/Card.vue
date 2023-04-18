<script>
export default {
    name: "Card",
    props: {
        card: Object
    }
}

</script>

<template>
    <div class="card h-100 text-center">
        <div class="card-image">
            <img class="card-img-top" :src="card.card_images[0].image_url_small" alt="">
        </div>
        <div class="card-name my-2">
            {{ card.name }}
        </div>
        <div class="archetype">
            {{ card.archetype }}
        </div>
    </div>
</template>

<style scoped lang="scss">
@use "../style/partials/variables" as *;

.card {
    background-color: $card-color;

    &-name {
        color: white;
    }
}
</style>