<template>
  <div>
  <span class="values">{{Cvalue}}</span>
  <input type='range' min='0' max='255' v-model='Cvalue' />
  <span class="demo" :style = "{ background: colorizer(color)}"></span>
  </div>
</template>

<script>

export default {
  name: 'colorSlider',
  data () {
    return {
      Cvalue: 0
    }
  },
  props: {
    color: String
  },
  methods: {
    colorizer (color) {
      if (color === 'red') {
        return 'rgb(' + this.Cvalue + ',0,0)'
      } else if (color === 'green') {
        return 'rgb(0,+' + this.Cvalue + ',0)'
      } else {
        return 'rgb(0,0,' + this.Cvalue + ')'
      }
    }
  }

}
</script>

<style scoped>
div {
  margin: 2%;
}

.values {
  font-size: 300%;
}

input {
  position: relative;
  left: 35px;
}

.demo {
  height: 10px;
  width: 10px;
  border-radius: 50%;
  padding: 10px;
  position: relative;
  left: 50px;
  display: inline-block;
  top: 5px;
}
</style>
