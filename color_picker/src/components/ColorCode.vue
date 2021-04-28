<template>
  <div class="ColorCode">
   <h3> HexCode:</h3>
   <input :value='rgbToHex(R,G,B)' />
  </div>
</template>

<script>

export default {
  name: 'ColorCode',
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
    }
  },
  data () {
    return {
      hex: '#7D7D7D'
    }
  },
  methods: {
    componentToHex (c) {
      var hex = c.toString(16)
      return hex.length === 1 ? '0' + hex : hex
    },
    rgbToHex (r, g, b) {
      return '#' + this.dec2base((((1 << 24) + (r << 16) + (g << 8) + b)), 16).slice(1)
    },
    dec2base (int, base) {
      const letters = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9', 'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K']
      let rest
      let returnVal = ''
      if (base > 1 && base < 37) {
        while (int !== 0) {
          rest = int % base
          int = Math.floor(int / base)
          returnVal = letters[rest] + returnVal
        }
      }
      return returnVal
    }
  }
}
</script>

<style scoped>
input {
  appearance: none;
  display: block;
  height: 25px;
  position: relative;
  font-size: 135%;
  width: 94%;
  margin: 6%;
  bottom: 15px;
  right: 15px;
  border-radius: 13px;
  background-color: #e9ecef;
  color: rgb(78, 78, 78);
  border-width: 0.35px;

}

input:active {
    border: none;
}

input:visited {
    border: none;
    outline-offset: none;
}

input:focus-visible {
    border: none;
     outline-offset: none;
     appearance: none;
     outline: none;
     border-style: solid;
     border-width: 0.35px;
}

</style>
