<template>
  <button :type="type" :class="mode">
  <slot> </slot>
  </button>
</template>

<script>
export default {
    props:['type','mode']

}
</script>

<style scoped>
button {
    padding: 0.75rem 1.5rem;
    font-family: inherit;
    background-color: #2ac408;
    border: 1px solid #3a0061;
    color: white;
    cursor: pointer;
    border-radius: 4px; 
    
}

button:hover,
button:active {
    background-color: #12a8e3;
    border-color: #270041;
    transition: 0.8s;
}

.flat {
    background-color: transparent;
    color: #0fe9f0;
    border: none;
}

.flat:hover,
.flat:active {
    background-color: #36b5f585;
    color:#ff00c3;
}

</style>

