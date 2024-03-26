<template >
    <storedRes :resources="savedresources"></storedRes>


</template>

<script> 
import storedRes from './components/learning-resource/storedRes.vue'

export default {
    components:{
        storedRes
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