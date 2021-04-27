<template>
  <span styl="{color: color}">(
    <input v-model="R"/>, <input v-model="G"/>, <input v-model="B"/> )</span>
</template>

<script>

export default {
  name: 'RGBbox',
  data () {
    return {
      R: 0,
      G: 0,
      B: 0
    }
  },
  props: {
    color: String
  }
}

</script>

<style scoped>
span {
  display: block;
  font-size: 2em;
}
input {
  width: 5%;
  border: none;
  background-color: gray;
  font-size: 20px;
}
</style>
