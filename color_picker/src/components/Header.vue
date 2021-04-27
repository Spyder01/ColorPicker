<template>
  <h1 :style='{color: color}'>{{text}}</h1>
</template>

<script>

export default {
  name: 'Header',
  props: {
    text: String,
    color: {
      type: String,
      default: 'yellow'
    }
  }
}
</script>

<style scoped>

h1{
  font-size:200%;
  text-align: center;
  margin-right: auto;
  margin-left: auto;
}

@media (max-width: 768px){
  span{
      font-size: 150%;
      margin: 1%;
  }
}
</style>
