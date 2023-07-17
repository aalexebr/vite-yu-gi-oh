<script>
import {store} from '../store';
export default{
    data(){
      return{
        store,
      }
    },
    components: {

    },
    props:{
        i:Number
    }
}
</script>

<template>
    <div class="my-col-25 p-2">
        <div class="row justify-content-center">
            
            <img :src="store.cards[i].card_images[0].image_url_small" alt="">
            
            <div class="text-center">
                <h4>
                    {{store.cards[i].name}}
                </h4>
                <span>
                    {{store.cards[i].archetype}}
                </span>
            </div>
        </div>    
    </div>
</template>

<style lang="scss" scoped>
    .my-col-25{
        width: 25%;
        border: 1px dotted red;
    }
</style>