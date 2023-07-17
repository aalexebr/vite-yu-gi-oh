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
}
</script>

<template>
  <HeaderComponent/>
  <MainComponent/>
</template>

<style lang="scss">
@use './assets/scss/main.scss' as *;
</style>
