<script>
import SingleCard from './SingleCard.vue';
import {store} from '../store';

export default{
    data(){
      return{
        store,
      }
    },
    components: {
        SingleCard
    },
}
</script>

<template>
    <main class="bg-primary-subtle">
        <div class="container py-3">
            <!-- <form action=""> -->
                <select name="" id="" class="m-3" v-model="store.selectType">
                    <option value="">Select your option</option>
                    <option v-for="(element,i) in store.archetypeArray" :key="i"
                    :value="store.archetypeArray[i].archetype_name">{{ store.archetypeArray[i].archetype_name }}</option>
                </select>
                
                <!-- <button type="submit">click</button>
            </form> -->
            <div class="card-container p-3">
                <div class="bg-secondary p-2">
                    found {{ store.cards.length }} cards
                </div>
                <div class="row">
                    <SingleCard class="my-card"
                    v-for="(singleCard, i) in store.cards" :key="i"
                    :i="i"/>
                </div>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
.card-container{
    background-color: white;
    &>.row{
        margin: 0 -10px;
    }

}

</style>