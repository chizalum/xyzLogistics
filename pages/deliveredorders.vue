<template>
  <div class="fullscreen">
    <div class="headdata">
      <input type="checkbox" class="box">
      <p class="headdata1">Tracking number</p>
      <p class="headdata2">Customer name</p>
      <p class="headdata3">Customer number</p>
      <p class="headdata4">Dispatch name</p>
      <p class="headdata5">Vehicle</p>
      <p class="headdata6">Location</p>
      <p class="headdata7">Package size</p>
      <p class="headdata8">Date</p>
    </div>
    <div class="bodydata" @click="showImage1()">
      <input type="checkbox" class="box1">
      <p class="bodydata1">18-6589929</p>
      <p class="bodydata2">Ajibike lola</p>
      <p class="bodydata3">0806573862587</p>
      <p class="bodydata4">Yusuf</p>
      <p class="bodydata5">Bike</p>
      <p class="bodydata6">Lekki</p>
      <p class="bodydata7">Small</p>
      <p class="bodydata8">10/2/22</p>
      <img src="droparrow.png" class="droparrow" :class="{rotate:turn1}"> 
    </div>
    <div class="viewcontainer" v-if="show1">
      <img src="deliveredview.png" class="orderview">
    </div>
    <div class="bodydata" @click="showImage2()">
      <input type="checkbox" class="box1">
      <p class="bodydata1">18-6589929</p>
      <p class="bodydata2">Ajibike lola</p>
      <p class="bodydata3">0806573862587</p>
      <p class="bodydata4">Yusuf</p>
      <p class="bodydata5">Bike</p>
      <p class="bodydata6">Lekki</p>
      <p class="bodydata7">Small</p>
      <p class="bodydata8">10/2/22</p>
      <img src="droparrow.png" class="droparrow" :class="{rotate:turn2}"> 
    </div>
    <div class="viewcontainer" v-if="show2">
      <img src="deliveredview.png" class="orderview">
    </div>
    <div class="bodydata" @click="showImage3()">
      <input type="checkbox" class="box1">
      <p class="bodydata1">18-6589929</p>
      <p class="bodydata2">Ajibike lola</p>
      <p class="bodydata3">0806573862587</p>
      <p class="bodydata4">Yusuf</p>
      <p class="bodydata5">Bike</p>
      <p class="bodydata6">Lekki</p>
      <p class="bodydata7">Small</p>
      <p class="bodydata8">10/2/22</p>
      <img src="droparrow.png" class="droparrow" :class="{rotate:turn3}"> 
    </div>
    <div class="viewcontainer" v-if="show3">
      <img src="deliveredview.png" class="orderview">
    </div>
    <div class="bodydata" @click="showImage4()">
      <input type="checkbox" class="box1">
      <p class="bodydata1">18-6589929</p>
      <p class="bodydata2">Ajibike lola</p>
      <p class="bodydata3">0806573862587</p>
      <p class="bodydata4">Yusuf</p>
      <p class="bodydata5">Bike</p>
      <p class="bodydata6">Lekki</p>
      <p class="bodydata7">Small</p>
      <p class="bodydata8">10/2/22</p>
      <img src="droparrow.png" class="droparrow" :class="{rotate:turn4}"> 
    </div>
    <div class="viewcontainer" v-if="show4">
      <img src="deliveredview.png" class="orderview">
    </div>
    <div class="bodydata" @click="showImage5()">
      <input type="checkbox" class="box1">
      <p class="bodydata1">18-6589929</p>
      <p class="bodydata2">Ajibike lola</p>
      <p class="bodydata3">0806573862587</p>
      <p class="bodydata4">Yusuf</p>
      <p class="bodydata5">Bike</p>
      <p class="bodydata6">Lekki</p>
      <p class="bodydata7">Small</p>
      <p class="bodydata8">10/2/22</p>
      <img src="droparrow.png" class="droparrow" :class="{rotate5:turn}"> 
    </div>
    <div class="viewcontainer" v-if="show5">
      <img src="deliveredview.png" class="orderview">
    </div>
    <div class="bodydata" @click="showImage6()">
      <input type="checkbox" class="box1">
      <p class="bodydata1">18-6589929</p>
      <p class="bodydata2">Ajibike lola</p>
      <p class="bodydata3">0806573862587</p>
      <p class="bodydata4">Yusuf</p>
      <p class="bodydata5">Bike</p>
      <p class="bodydata6">Lekki</p>
      <p class="bodydata7">Small</p>
      <p class="bodydata8">10/2/22</p>
      <img src="droparrow.png" class="droparrow" :class="{rotate6:turn}"> 
    </div>
    <div class="viewcontainer" v-if="show6">
      <img src="deliveredview.png" class="orderview">
    </div>
    <div class="bodydata" @click="showImage7()">
      <input type="checkbox" class="box1">
      <p class="bodydata1">18-6589929</p>
      <p class="bodydata2">Ajibike lola</p>
      <p class="bodydata3">0806573862587</p>
      <p class="bodydata4">Yusuf</p>
      <p class="bodydata5">Bike</p>
      <p class="bodydata6">Lekki</p>
      <p class="bodydata7">Small</p>
      <p class="bodydata8">10/2/22</p>
      <img src="droparrow.png" class="droparrow" :class="{rotate7:turn}"> 
    </div>
    <div class="viewcontainer" v-if="show7">
      <img src="deliveredview.png" class="orderview">
    </div>
    <div class="bodydata" @click="showImage8()">
      <input type="checkbox" class="box1">
      <p class="bodydata1">18-6589929</p>
      <p class="bodydata2">Ajibike lola</p>
      <p class="bodydata3">0806573862587</p>
      <p class="bodydata4">Yusuf</p>
      <p class="bodydata5">Bike</p>
      <p class="bodydata6">Lekki</p>
      <p class="bodydata7">Small</p>
      <p class="bodydata8">10/2/22</p>
      <img src="droparrow.png" class="droparrow" :class="{rotate8:turn}"> 
    </div>
    <div class="viewcontainer" v-if="show8">
      <img src="deliveredview.png" class="orderview">
    </div>
    <div class="bodydata" @click="showImage9()">
      <input type="checkbox" class="box1">
      <p class="bodydata1">18-6589929</p>
      <p class="bodydata2">Ajibike lola</p>
      <p class="bodydata3">0806573862587</p>
      <p class="bodydata4">Yusuf</p>
      <p class="bodydata5">Bike</p>
      <p class="bodydata6">Lekki</p>
      <p class="bodydata7">Small</p>
      <p class="bodydata8">10/2/22</p>
      <img src="droparrow.png" class="droparrow" :class="{rotate9:turn}"> 
    </div>
    <div class="viewcontainer" v-if="show9">
      <img src="deliveredview.png" class="orderview">
    </div>
    <div class="bodydata" @click="showImage10()">
      <input type="checkbox" class="box1">
      <p class="bodydata1">18-6589929</p>
      <p class="bodydata2">Ajibike lola</p>
      <p class="bodydata3">0806573862587</p>
      <p class="bodydata4">Yusuf</p>
      <p class="bodydata5">Bike</p>
      <p class="bodydata6">Lekki</p>
      <p class="bodydata7">Small</p>
      <p class="bodydata8">10/2/22</p>
      <img src="droparrow.png" class="droparrow" :class="{rotate10:turn}"> 
    </div>
    <div class="viewcontainer" v-if="show10">
      <img src="deliveredview.png" class="orderview">
    </div>
    
  </div>
</template>

<script>
export default {
  name: 'deliveredorders',
  layout: 'orders',
  data() {
    return {
      show10: false,
      turn10: false,
      show1: false,
      turn1: false,
      show2: false,
      turn2: false,
      show3: false,
      turn3: false,
      show4: false,
      turn4: false,
      show5: false,
      turn5: false,
      show6: false,
      turn6: false,
      show7: false,
      turn7: false,
      show8: false,
      turn8: false,
      show9: false,
      turn9: false,
    }
  },
  methods: {
    showImage1() {
      this.show1 = !this.show1;
      this.turn1 = !this.turn1;
    },
    showImage2() {
      this.show2 = !this.show2;
      this.turn2 = !this.turn2;
    },
    showImage3() {
      this.show3 = !this.show3;
      this.turn3 = !this.turn3;
    },
    showImage4() {
      this.show4 = !this.show4;
      this.turn4 = !this.turn4;
    },
    showImage5() {
      this.show5 = !this.show5;
      this.turn5 = !this.turn5;
    },
    showImage6() {
      this.show6 = !this.show6;
      this.turn6 = !this.turn6;
    },
    showImage7() {
      this.show7 = !this.show7;
      this.turn7 = !this.turn7;
    },
    showImage8() {
      this.show8 = !this.show8;
      this.turn8 = !this.turn8;
    },
    showImage9() {
      this.show9 = !this.show9;
      this.turn9 = !this.turn9;
    },
    showImage10() {
      this.show10 = !this.show10;
      this.turn10 = !this.turn10;
    },
  },
}
</script>

<style scoped>
.fullscreen{
height: 100vh;
width: 100vw;
white-space: nowrap;
margin: 0 0 0 0;
background: #FFFEFA;
}

.headdata{
display: flex;
flex-direction: row;
margin: 32px 0 0 368px;
}

.box{
margin: 0 0 0 0;
}

.headdata1{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 32px;
}

.headdata2{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 40px;
}

.headdata3{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 40px;
}

.headdata4{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 40px;
}

.headdata5{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 40px;
}

.headdata6{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 40px;
}

.headdata7{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 40px;
}

.headdata8{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 40px;
}

.bodydata{
display: flex;
flex-direction: row;
width: 1090px;
height: 56px;
background: #FFFFFF;
border: 1px solid #E4E4E4;
margin: 16px 0 0 344px;
}

.box1{
margin: auto 0 auto 24px;

}

.bodydata1{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #000000;
margin: auto 0 auto 32px;
}

.bodydata2{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #000000;
margin: auto 0 auto 73px;
}

.bodydata3{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #000000;
margin: auto 0 auto 66px;
}

.bodydata4{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #000000;
margin: auto 0 auto 49px;
}

.bodydata5{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #000000;
margin: auto 0 auto 100px;
}

.bodydata6{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #000000;
margin: auto 0 auto 57px;
}

.bodydata7{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #000000;
margin: auto 0 auto 60px;
}

.bodydata8{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #000000;
margin: auto 0 auto 84px;
}

.droparrow{
width: 8px;
height: 4px;
margin: auto 0 auto 44px;
}

.orderview{
margin: 0 0 0 0;
width: 100%;
}

.viewcontainer{
margin: 0 0 0 304px;
padding: 0 0 0 0;
height: 430px;
width: 1057px;
}

.rotate{
transform: rotate(180deg);
}
</style>
