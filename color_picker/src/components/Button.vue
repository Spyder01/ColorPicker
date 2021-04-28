<template>
<button class="btn" @click='onClick' type="button" :style="{background: Color}"  >{{Text}}</button>
</template>

<script>
export default {
  name: 'Button',
  props: {
    Text: String,
    Color: String
  },
  methods: {
    onClick () {
      this.$emit('toggle')
    }
  }
}
</script>
<style scoped>
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 2px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
  box-shadow: 0 2px 10px rgba(0,0,0,0.5);
  transition: 0.5s ease-out-in;
}
.btn:hover {
  transform: scale(1.09,1.09);
  box-shadow: 1px 6px 15px rgba(0,0,0,0.5);
  -webkit-filter: grayscale(25%);
  filter: grayscale(50%);
  -webkit-filter: blur(20%);
  filter: blur(20%);
}
</style>