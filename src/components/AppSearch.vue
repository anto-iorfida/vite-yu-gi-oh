<script>
import { store } from '../store.js';
import axios from 'axios';

    export default {
        name: "AppSearch",
        data(){
                return{
                    store,
                    availableStatuses: [],
                    // availableStatuses: [
                    //     'Alien',
                    //     'Blackwing',
                    //     'Crystal',
                    //     'Deskbot',
                    //     'Favorite'
                    // ],
                }
            },
            methods:{
                getGenerateArchetype(){
                    axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
                        .then((response) => {
                            console.log(response.data);
                            this.availableStatuses = response.data

                        });
                }
            },
            mounted(){
                this.getGenerateArchetype();
            }
        }
</script>

<template>
<section>
    <div class="container">
        <select v-model="store.searchedArchetype">
                <option value="">Scegli uno status</option>
                <!-- Scelte disponibili -->
                <option v-for="status in availableStatuses" :value="status">{{ status.archetype_name }}</option>
        </select>
        <button @click="$emit('searchPerfomed')">Cerca</button>
    </div>
</section>
</template>

<style lang="scss" scoped>
    select{
        border: 2px solid darkred;
        padding: 5px 10px;
        border-radius: 10px 10px 0 0;
        &:hover{
             color: gray;
        }
    }
    button{
        border: 2px solid darkred;
        padding: 6px 10px;
        border-radius: 10px 10px 0 0;
        &:hover{
             color: gray;
        }
    }
</style>