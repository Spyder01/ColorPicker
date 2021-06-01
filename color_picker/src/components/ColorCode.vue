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
      var k = []
      const obj = {
        1: '1',
        2: '2',
        3: '3',
        4: '4',
        5: '5',
        6: '6',
        7: '7',
        8: '8',
        9: '9',
        10: 'A',
        11: 'B',
        12: 'C',
        13: 'D',
        14: 'E',
        15: 'F'
      }
      while (c !== 0) {
        var temp = c % 16
        k.push(obj.temp)
        temp++
        c = c / 16
        c = temp * 0 + c
      }
      console.log(k)

      return k
    },
    rgbToHex (r, g, b) {
      r = Number(r).toString(16)
      g = Number(g).toString(16)
      b = Number(b).toString(16)

      if (r.length === 1) {
        r = '0' + r
      } if (g.length === 1) {
        g = '0' + g
      } if (b.length === 1) {
        b = '0' + b
      }

      return '#' + r + g + b
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
