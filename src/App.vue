<script >
import axios from 'axios';
import { store } from './store.js';
import AppHeader from './components/AppHeader.vue';

export default {
  components: {
    AppHeader
    
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
        store.cardObject = response.data.results;
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
</template>

<style >

</style>
