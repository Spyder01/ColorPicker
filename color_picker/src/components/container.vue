<template>
  <div class='container'>
  <Header text = "ColorPicker" color = "black"/>
  <RGBbox color = "black" />
  </div >
</template>

<script>
import Header from './Header'
import RGBbox from './RGBbox'
export default {
  name: 'Container',
  components: {
    Header,
    RGBbox
  }
}
</script>

<style scoped>
.container{
   max-width: 35%;
   min-height: 45%;
   padding: 0.1% 1% 0.1% 1%;
   margin: 10% auto;
   margin-top: 17%;
   border-radius: 3px;
   box-shadow:0 0 0.7rem rgba(0, 0, 0, 0.4);
}

@media (max-width: 768px){

.container{
   max-width: 85%;
   min-height: 45%;
   padding: 0.1% 1% 0.1% 1%;
   margin: 10% auto;
   margin-top: 50%;
   border-radius: 3px;
   box-shadow:0 0 0.7rem rgba(0, 0, 0, 0.4);
}

}
</style>
