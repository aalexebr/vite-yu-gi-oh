<script>
import axios from 'axios';
import componentTemplate from './components/componentTemplate.vue';
import HeaderComponent from './components/HeaderComp.vue';
import MainComponent from './components/MainComp.vue';
import {store} from './store';

export default{
    data(){
      return{
        store,
      }
    },
    components: {
      HeaderComponent,
      MainComponent,
    },
    methods:{
      getCards(){
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0')
        .then(response=>{
        // console.log(response.data.data)
        this.store.cards = response.data.data;
        // console.log(store.cards[0])
      })
      .catch(error=>{

      })
      },
      getArchetypeList(){
        axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php').then(response=>{
        // console.log(response.data[0].archetype_name)
        this.store.archetypeArray = response.data
        // console.log(this.store.archetypeArray[0].archetype_name)
        console.log(this.store.selectType)
      })
      }
    },
    mounted(){
      this.getCards();
      this.getArchetypeList();
    }
}
</script>

<template>
  <HeaderComponent/>
  <MainComponent/>
</template>

<style lang="scss">
@use './assets/scss/main.scss' as *;
</style>
