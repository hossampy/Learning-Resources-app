<template>
    <LearnigResources v-for="Resource in savedResources" :key="Resource.id"></LearnigResources>
</template>

<script>
import LearnigResources from './componets/LearnigResources/LearnigResources.vue'
export default {
    components:{
        LearnigResources
    },
data(){
    return{
        savedResources:[
            {
             id:'vuejs',
             title:'documents',
             description:'official documents',
             linke:'vuejs.org'
            },
            {
             id: 'google',
             title: 'documents google',
            description: 'google documents',
            linke: 'google.com'
            }
        ]
    }
}
}
</script>

<style>

</style>