<template>
  <header>
    <h1>{{ title }}</h1>
  </header>
</template>

<script>
export default { 
props:['title']
}
</script>

<style scoped>
header {
    width: 100%;
    height: 5rem;
    background-color: #36b5f585;
    display: flex;
    justify-content: center;
    align-items: center;
}

header h1 {
    color: white;
    margin: 0;
    text-transform: capitalize;
}
</style>