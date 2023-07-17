<script>
import axios from 'axios';
import componentTemplate from './components/componentTemplate.vue';
import {store} from './store';

export default{
    data(){
      return{
        store,
      }
    },
    components: {
      componentTemplate
    },
}
</script>

<template>
  {{ store.text }}
  <componentTemplate/>
</template>

<style lang="scss">
@use './assets/scss/main.scss' as *;
</style>
