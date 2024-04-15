<script >
import axios from 'axios';
import { store } from './store.js';
import AppHeader from './components/AppHeader.vue';
import sectionCard from './components/sectionCard.vue';

export default {
  components: {
    AppHeader,
    sectionCard
    
  },
  data() {
    return {
      store
    };
  },
  methods: {
    getcardObjectFromApi() {
      // Prende le carte dall'api e popola il main
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
      .then((response) => {
        store.cardObject = response.data.data;
        console.log(response);
      });
    }
  },
  mounted() {
    this.getcardObjectFromApi();
  }

}
</script>

<template>
<AppHeader></AppHeader>

<main>
  <sectionCard></sectionCard>
</main>
</template>

<style lang="scss">
@use './style/generic';

</style>
