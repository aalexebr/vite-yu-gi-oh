<script>
import SingleCard from './SingleCard.vue';
import {store} from '../store';
import axios from 'axios';
export default{
    data(){
      return{
        store,
        cards : []
      }
    },
    components: {
        SingleCard
    },
    created(){
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0').then(response=>{
        // console.log(response.data.data)
        this.cards = response.data.data;
        // console.log(store.cards[0].name)
      })
    }
}
</script>

<template>
    <main class="bg-primary-subtle">
        <div class="container py-3">
            <select name="" id="" class="m-3">

            </select>
        
            <div class="card-container p-3">
                <div class="bg-secondary p-2">
                    found
                </div>
                <div class="row">
                    <SingleCard class="px-3"
                    v-for="(singleCard, i) in store.cards" :key="i"
                    :i="i"/>
                    <!-- <div class="my-col-25 p-2">
                            <div class="row justify-content-center"
                                v-for="(singleCard, i) in cards" :key="i">
                                
                                <img :src="singleCard.card_images[0].image_url_small" alt="">
                                
                                <div class="text-center">
                                    <h4>
                                        {{singleCard.name}}
                                    </h4>
                                    <span>
                                        {{singleCard.archetype}}
                                    </span>
                                </div>
                            </div>
                    </div> -->
                </div>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
.card-container{
    background-color: white;
}
.my-col-25{
        width: 20%;
        border: 1px dotted red;
    }
</style>