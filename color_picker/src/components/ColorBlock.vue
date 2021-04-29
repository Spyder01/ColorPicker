<template>
 <div>
  <div v-show='decider'  class="ColorBlock" :style="{ background: Colorizer(R,G,B) }">
     </div>
  <div> <input @dblclick="onClick()" v-show='!decider' placeholder='Type Text' class="ColorBlock" :style="{ background: Color, color: Colorizer(R,G,B) }" >
 </div>
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
  data () {
    return {
      Color: 'white',
      decider2: true
    }
  },
  methods: {
    Colorizer (R, G, B) {
      const color = 'rgb(' + R + ',' + G + ',' + B + ')'
      return color
    },
    onClick () {
      this.Color = 'white'
      this.decider2 = !this.decider2
      if (this.decider2 === false) {
        this.Color = 'black'
      }
    }
  }
}
</script>

<style scoped>

.ColorBlock {
  display: block;
  margin: 6%;
  width: 90%;
  height: 60px;
  box-shadow:0 0 0.7rem rgba(0, 0, 0, 0.4);
  transition: 0.7s ease-in-out;
  font-size: 200%;
  border-radius: 8px;
  position: relative;
  bottom: 15px;
  right: 4px;
  border-width: 1px;
  border-color: gray;
  outline: none;
}

input:focus {
  appearance: none;
}

</style>
