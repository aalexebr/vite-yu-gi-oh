<script>
import SingleCard from './SingleCard.vue';
export default{
    data(){
      return{
        
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
            <select name="" id="" class="m-3">

            </select>
        
            <div class="card-container p-3">
                <div class="bg-secondary p-2">
                    found
                </div>
                <div class="row">
                    <SingleCard/>
                </div>

            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
.card-container{
    background-color: white;
}
</style>