<script>
export default {
    name: "Card",
    props: {
        card: Object
    }
}

</script>

<template>
    <div class="card text-center">
        <div class="card-image">
            <img :src="card.card_images[0].image_url_small" alt="">
        </div>
        <div class="card-name my-2">
            {{ card.name }}
        </div>
        <div class="race">
            {{ card.race }}
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