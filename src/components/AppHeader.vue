<script>
export default {
    name: "AppHeader",
    data() {
        return {

        }
    }
}
</script>

<template>
    <header>
        <h1>Yu-Gi-Oh Api</h1>
    </header>
</template>

<style scoped lang="scss">
@use "../style/partials/variables" as *;

header {
    height: $header-height;
    color: white;
    background-color: $header-color;

    h1 {
        line-height: $header-height;
    }
}
</style>