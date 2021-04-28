<template>
 <div>
  <div v-show='decider'  class="ColorBlock" :style="{ background: Colorizer(R,G,B) }">
     </div>
  <input v-show='!decider' class="ColorBlock" :style="{ color: Colorizer(R,G,B) }">
 </div>
</template>

<script>
export default {
  name: 'ColorBlock',
  props: {
    R: Number,
    G: Number,
    B: Number,
    decider: {
      type: Boolean,
      default: true
    }
  },
  methods: {
    Colorizer (R, G, B) {
      const color = 'rgb(' + R + ',' + G + ',' + B + ')'
      return color
    }
  }
}
</script>

<style scoped>

.ColorBlock {
  display: block;
  margin: 6%;
  width: 90%;
  height: 50px;
  box-shadow:0 0 0.7rem rgba(0, 0, 0, 0.4);
  transition: 0.7s ease-in-out;
  font-size: 220%;
}

</style>
