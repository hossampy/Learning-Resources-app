<template>
    <LearnigResources v-for="res in resources" :key="res.id" :title="res.title" :description="res.description"
        :link="res.link"></LearnigResources>


</template>

<script>
import LearnigResources from './LearningResource.vue'
export default {
    inject: [
        'resources'
    ],
    components:{
        LearnigResources
    },
    data(){
        return{
           
        }
    },
   
    
}
</script>

<style>
ul {
    list-style:none;
    margin: 0;
    padding: 0;
    margin: auto;
    max-width: 40rem;
}

</style>