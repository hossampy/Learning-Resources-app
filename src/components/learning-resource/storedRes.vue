<template>
    <LearnigResources v-for="resource in resources" :key="resource.id" :title="resource.title"
        :description="resource.description" :link="resource.link"></LearnigResources>


</template>

<script>
import LearnigResources from './LearnigResources.vue'
export default {
    props:[
        'resources'
    ],
    components:{
        LearnigResources
    }

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