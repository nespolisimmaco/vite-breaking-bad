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
    this.getCards();
  },
  methods: {
    getCards() {
      this.store.loading = true;
      const params = {
        num: 20,
        offset: 0,
      };
      if (this.store.selectedArchetype) {
        params.archetype = this.store.selectedArchetype;
      }
      axios
        .get(store.apiURL, {
          params
        })
        .then((resp) => {
          const myData = resp.data.data;
          console.log(myData);
          this.store.cards = myData;
          this.store.loading = false;
        })
    },
    handleFilter() {
      this.getCards();
    }
  }
}
</script>

<template>
  <AppHeader />
  <SelectArchetype @filter="handleFilter" />
  <CardsList />
</template>

<style lang="scss">
@use "./style/general.scss";
</style>