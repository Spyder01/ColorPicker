<template>
  <div class='container' :style='{background: color}'>
  <Header text = "ColorPicker" color = "black"/>
  <button class="btn" type="button" @click="OnClick3()" :style='{background: bColor3 }' id="btn3">ChangeTheme</button>
  <RGBbox :R='R' :G ='G' :B='B'  color="rgb( 227, 84, 97 )" />
  <colorSlider @Send-Color="SendColorR" color='red'/>
  <colorSlider @Send-Color="SendColorG" color='green'/>
  <colorSlider @Send-Color="SendColorB" color='blue'/>
  <ColorCode :R='R' :G ='G' :B='B'  />
  <ColorBlock :R='R' :G ='G' :B='B' :decider='decider' />
  <button @click="OnClick()" id='btn' class="btn" type="button" :style='{background: bColor }' >{{bText}}</button>
  <button class="btn" type="button" @click="OnClick2()" :style='{background: bColor2 }' id="btn2">{{bText2}}</button>
  </div >
</template>

<script>
import Header from './Header'
import RGBbox from './RGBbox'
import colorSlider from './colorSlider'
import ColorBlock from './ColorBlock'
import ColorCode from './ColorCode'
export default {
  name: 'Container',
  data () {
    return {
      R: 125,
      G: 125,
      B: 125,
      decider: true,
      decider2: true,
      bColor: 'teal',
      bText: 'BlockView',
      bText2: 'ChangeBackground',
      bColor2: 'rgb( 226, 62, 59 )',
      bColor3: 'rgb( 61, 208, 99 )',
      MText: 'rgb( 65, 199, 77 )',
      MBgColor: 'rgba(32,33,36,1)',
      MTextBox: 'black',
      color: 'white'
    }
  },
  components: {
    Header,
    RGBbox,
    colorSlider,
    ColorBlock,
    ColorCode
  },
  methods: {
    SendColorR (Value) {
      this.R = Value
    },
    SendColorG (Value) {
      this.G = Value
    },
    SendColorB (Value) {
      this.B = Value
    },
    OnClick () {
      this.bText = 'BlockView'
      this.decider = !this.decider
      if (this.decider === false) {
        this.bText = 'TextView'
      }
    },
    OnClick2 () {
      document.body.style.backgroundColor = 'rgb(' + this.R + ',' + this.G + ',' + this.B + ')'
    },
    OnClick3 () {
      this.decider2 = !this.decider2
      if (this.decider2 === false) {
        document.body.style.backgroundColor = 'rgb(125,125,125)'
        this.color = 'black'
      } else {
        document.body.style.backgroundColor = 'rgb(125,125,125)'
        this.color = 'white'
      }
    }
  }
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Raleway&display=swap');
.container{
   max-width: 30%;
   min-height: 45%;
   padding: 0.1% 1% 0.1% 1%;
   margin: 10% auto;
   margin-top: 4%;
   border-radius: 10%;
   box-shadow:0 0 0.7rem rgba(0, 0, 0, 0.4);
   position: relative;
   color: rgb( 227, 84, 97 );
}

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
  font-family: 'Raleway', sans-serif;
  position: relative;
  bottom: 12px;
  left: 12px;

}

#btn {
  background-color: teal;
}

#btn:hover {
   -webkit-filter: grayscale(25%);
  filter: grayscale(50%);
}

.btn:hover {
  transform: scale(1.09,1.09);
  box-shadow: 1px 6px 15px rgba(0,0,0,0.5);
  -webkit-filter: blur(20%);
  filter: blur(20%);
}

.btn:active{
  transform: scale(1,1);
}

#btn2 {
   left: 40px;
}

#btn3 {
      left: 29%;
}

@media (max-width: 768px){

.container{
   max-width: 90%;
   min-height: 50%;
   padding: 0.1% 1% 0.1% 1%;
   margin: 10% auto;
   margin-top: 7%;
   right: 8px;
   border-radius: 10%;
   box-shadow:0 0 0.7rem rgba(0, 0, 0, 0.4);
   transform: scale(1,0.89);
}

#btn3 {
      left: 80px;
}

#btn2 {
   left: 9px;
}

}
</style>
