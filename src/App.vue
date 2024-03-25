<template >
    <LearnigResources v-for="res in savedresources" :key="res.id" :title="res.title" :description="res.description"
        :link="res.link"></LearnigResources>


</template>

<script>
import LearnigResources from './components/learning-resource/LearnigResources.vue'
export default {
    components:{
        LearnigResources
    },
data(){
    return{
        savedresources:[
            {
             id:'vuejs',
             title:'documents',
             description:'official documents',
            link:'vuejs.org'
            },
            {
             id: 'google',
             title: 'documents google',
            description: 'google documents',
            link: 'google.com'
            }
        ]
    }
}
}
</script>

<style>

</style>