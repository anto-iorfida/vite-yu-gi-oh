<script>
import { store } from '../store.js';

    export default {
        name: "AppSearch",
        data(){
                return{
                    store,
                    availableStatuses: [
                        'Alien',
                        'Blackwing',
                        'Crystal',
                        'Dark Magician',
                        'Favorite'
                    ],
                }
            } 
        }
</script>

<template>
<section>
    <div class="container">
        <select v-model="store.searchedStatus">
                <option value="">Scegli uno status</option>
                <!-- Scelte disponibili -->
                <option v-for="status in availableStatuses" :value="status">{{ status }}</option>
        </select>
        <button>Cerca</button>
    </div>
</section>
</template>

<style lang="scss" scoped>

</style>