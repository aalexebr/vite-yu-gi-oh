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
    mounted(){
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0').then(response=>{
        console.log(response.data.data)
        this.store.cards = response.data.data;
        console.log('array new',this.store.cards)
      })
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
