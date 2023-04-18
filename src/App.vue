<script>
import { store } from './store';
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import CardsList from "./components/CardsList.vue";
import SelectArchetype from './components/SelectArchetype.vue';

export default {
  components: {
    AppHeader,
    CardsList,
    SelectArchetype
  },
  data() {
    return {
      store
    }
  },
  mounted() {
    this.store.loading = true;
    axios
      .get(store.apiURL)
      .then((resp) => {
        console.log(resp);
        const myData = resp.data.data;
        console.log(myData);
        this.store.cards = myData;
        this.store.loading = false;
      })
  }
}
</script>

<template>
  <AppHeader />
  <SelectArchetype />
  <CardsList />
</template>

<style lang="scss">
@use "./style/general.scss";
</style>