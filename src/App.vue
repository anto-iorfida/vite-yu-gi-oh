<script >
import axios from 'axios';
import { store } from './store.js';
import AppHeader from './components/AppHeader.vue';
import sectionCard from './components/sectionCard.vue';
import AppSearch from './components/AppSearch.vue';


export default {
  components: {
    AppHeader,
    sectionCard,
    AppSearch
    
    
  },
  data() {
    return {
      store
    };
  },
  methods: {
    getArchetypeFromApi() {

      let apiUrl = 'https://db.ygoprodeck.com/api/v7/cardinfo.php'

      const queryParams= { 
        
        num: 20,
        offset: 0
      };
      if(store.searchedArchetype !== '') {
        queryParams.archetype = store.searchedArchetype;
        
      }

console.log(queryParams.archetype);

      // Prende le carte dall'api e popola il main
      axios.get(apiUrl, {
        params: queryParams
      })
      .then((response) => {
        store.cardObject = response.data.data;
        store.isLoading = false;
        
      });
    }
  },
  mounted() {
    this.getArchetypeFromApi();
  }

}
</script>

<template>
<AppHeader></AppHeader>

<main>
  <AppSearch @searchPerfomed="getArchetypeFromApi"></AppSearch>
  <sectionCard ></sectionCard>
  
</main>
</template>

<style lang="scss">
@use './style/generic';

</style>
