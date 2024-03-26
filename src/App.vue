<template >
    <TheHeader :title="title1"> </TheHeader>
    <TheRes ></TheRes>
    
    </template>

<script> 

import TheHeader from './components/layouts/TheHeader.vue'
import TheRes from './components/learning-resource/TheResources.vue'

export default {
    components:{
        TheRes,
        TheHeader
    },
data(){
    return{
        title1:'remmberme',
     
    }
}
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
    box-sizing: border-box;
}

html {
    font-family: 'Roboto', sans-serif;
}

body {
    margin: 0;
}

</style>