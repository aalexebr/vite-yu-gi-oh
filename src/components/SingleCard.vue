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
    <div class="my-col-25 p-2 bg-primary-subtle">
        <div class="row justify-content-center">
            
            <img :src="store.cards[i].card_images[0].image_url" alt="">
            
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
        width: calc((100% / 5) - 20px);
        border: 1px dotted red;
        margin: 10px;
    }
</style>