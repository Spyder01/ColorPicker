<template>
  <span :style="{color: color}">rgb( {{R}}, {{G}}, {{B}} )</span>
</template>

<script>

export default {
  name: 'RGBbox',
  props: {

    R: {
      type: Number,
      default: 125
    },
    G: {
      type: Number,
      default: 125
    },
    B: {
      type: Number,
      default: 125
    },
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
  font-size: 10px;

}
</style>
