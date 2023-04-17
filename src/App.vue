<script>
import { store } from './store';
import axios from "axios";

export default {
  data() {
    return {
      store
    }
  },
  mounted() {
    axios
      .get(store.apiURL)
      .then((resp) => {
        console.log(resp);
        const myData = resp.data.data;
        console.log(myData);
        this.store.cards = myData;
      })
  }
}
</script>

<template></template>

<style lang="scss">
@use "./style/general.scss";
</style>