<template>
  <h1>{{text}}</h1>
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
  font-size:250%;
  text-align: center;
  margin-right: auto;
  margin-left: auto;
  background: -webkit-linear-gradient(#7FD9D9,rgb( 101, 174, 64 ));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

@media (max-width: 768px){
  span{
      font-size: 150%;
      margin: 1%;
  }
}
</style>
