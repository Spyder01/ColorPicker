<template>
  <div>
  <span class="values">{{Value}}</span>
  <input type='range' min='0' max='255' v-model='Value'/>
  <span class="demo" :style = "{ background: colorizer(color)}"></span>
  </div>
</template>

<script>

export default {
  name: 'colorSlider',
  data () {
    return {
      Value: 125
    }
  },
  props: {
    color: String,
    Cvalue: Number
  },
  methods: {
    colorizer (color) {
      this.$emit('Send-Color', this.Value)
      if (color === 'red') {
        return 'rgb(' + this.Value + ',0,0)'
      } else if (color === 'green') {
        return 'rgb(0,+' + this.Value + ',0)'
      } else {
        return 'rgb(0,0,' + this.Value + ')'
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
  display: inline-block;
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
  box-shadow:0 0 0.2rem rgba(0, 0, 0, 0.4);
  transition: 0.7s ease-in-out;
}
</style>
