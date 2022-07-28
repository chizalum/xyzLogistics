<template>
  <div>
  <div class="viewcontainer1" :class="{viewcontainer: showMore}" v-for="(details, index) in packageDetails" :key="index">
        <div class="first-column">
          <div class="details-section">
            <p class="pick-up">Pickup<span class="pick" v-if="details.showMore">(Local)</span></p>
            <div class="more-details" @click="changeView(index)" v-if="details.showLess">
              <p class="details-text">More Details</p>
              <img src="gold-dropdown.png" class="gold-dropdown">
            </div>
          </div>
          <div class="first-row">
            <img src="directionarrows.png" class="direction-arrows">
            <p class="from">From</p>
            <img src="locator.png" class="locator-img">
            <p class="locator-text">12 Odutola street, Adaba B/stp, Egbeda, Lagos.</p>
          </div>
          <div class="second-row">
            <p class="to">To</p>
            <img src="locator.png" class="locator-img2">
            <p class="locator-text">12 Odutola street, Adaba B/stp, Egbeda, Lagos.</p>
          </div>
          <div v-if="details.showMore">
            <hr class="info-rule">
            <div class="third-row">
              <img src="profile-icon.png" class="profile-icon">
              <p class="from2">From</p>
              <img src="profilepic.png" class="profilepic">
              <p class="locator-name">Ajibike Lola</p>
            </div>
            <div class="fourth-row">
              <img src="phone.png" class="phone">
              <p class="number">07064783993</p>
            </div>
            <div class="fifth-row">
              <p class="to2">To</p>
              <img src="profilepic.png" class="profilepic2">
              <p class="locator-name">Ajibike Lola</p>
            </div>
            <div class="sixth-row">
              <img src="phone.png" class="phone">
              <p class="number">07064783993</p>
            </div>
            <hr class="info-rule">
          </div>
          <div class="seventh-row">
            <img src="clock.png" class="clock">
            <p class="date">Date</p>
            <p class="time">Time</p>
            <p class="package">Package Size</p>
            <button class="assign-btn2" v-if="details.showLess" @click="changeView(index)">Assign</button>
          </div>
          <div class="eight-row">
            <p class="date1">12/03/22</p>
            <p class="time1">10am</p>
            <p class="package1">Medium</p>
          </div>
          <div class="nine-row" v-if="details.showMore">
            <button class="assign-btn" @click="openModal()">Assign</button>
            <button class="cancel-btn" @click="changeView(index)">Cancel Order</button>
          </div>
        </div>
        <div class="second-column">
          <img :src="details.img[details.number]" :class="{columnimg: showMore}">
        </div>
      </div>
      <pendingmodal v-if="showModal" @closeModal="offModal()"  />
  </div>    
</template>

<script>
export default {
  name: 'pendingorders',
  layout: 'orders',

  data() {
    return {
      showModal: false,
      packageDetails: [
        {
          index: 1,
          date: '10/2/22',
          number: 0,
          showLess: true,
          showMore: false,
          img: ["pending.png", "orders-img.png"],
          show: 'false',
          turn: 'false',
        },
        {
          index: 2,
          date: '10/2/22',
          number: 0,
          showLess: true,
          showMore: false,
          img: ["pending.png", "orders-img.png"],
          show: 'false',
          turn: 'false',
        },
        {
          index: 3,
          date: '10/2/22',
          number: 0,
          showLess: true,
          showMore: false,
          img: ["pending.png", "orders-img.png"],
          show: 'false',
          turn: 'false',
        },
        {
          index: 4,
          date: '10/2/22',
          number: 0,
          showLess: true,
          showMore: false,
          img: ["pending.png", "orders-img.png"],
          show: 'false',
          turn: 'false',
        },
        {
          index: 5,
          date: '10/2/22',
          number: 0,
          showLess: true,
          showMore: false,
          img: ["pending.png", "orders-img.png"],
          show: 'false',
          turn: 'false',
        },
        {
          index: 6,
          date: '10/2/22',
          number: 0,
          showLess: true,
          showMore: false,
          img: ["pending.png", "orders-img.png"],
          show: 'false',
          turn: 'false',
        },
        {
          index: 7,
          date: '10/2/22',
          number: 0,
          showLess: true,
          showMore: false,
          img: ["pending.png", "orders-img.png"],
          show: 'false',
          turn: 'false',
        },
        {
          index: 8,
          date: '10/2/22',
          number: 0,
          showLess: true,
          showMore: false,
          img: ["pending.png", "orders-img.png"],
          show: 'false',
          turn: 'false',
        },
        {
          index: 9,
          date: '10/2/22',
          number: 0,
          showLess: true,
          showMore: false,
          img: ["pending.png", "orders-img.png"],
          show: 'false',
          turn: 'false',
        },
        {
          index: 10,
          date: '10/2/22',
          number: 0,
          showLess: true,
          showMore: false,
          img: ["pending.png", "orders-img.png"],
          show: 'false',
          turn: 'false',
        },
        {
          index: 11,
          date: '10/2/22',
          number: 0,
          showLess: true,
          showMore: false,
          img: ["pending.png", "orders-img.png"],
          show: 'false',
          turn: 'false',
        },
        ]
    }
  },

  methods: {
    changeView(index) {
      this.packageDetails[index].showLess = !this.packageDetails[index].showLess;
      this.packageDetails[index].showMore = !this.packageDetails[index].showMore;
      this.seeMore = true;
       if(this.packageDetails[index].number < 1){
            this.packageDetails[index].number++
    }else{
           this.packageDetails[index].number = 0
    };
      },

    openModal() {
      this.showModal = true;
    },

    offModal() {
          this.showModal = false
        },
    }
  }
</script>

<style scoped>

.viewcontainer{
height: 485px;
width: 1057px;
}

.viewcontainer1{
margin: 24px 0 0 344px;
display: flex;
flex-direction: row;
min-height: 239px;
height: auto;
width: 1057px;
background: #FFFFFF;
border: 1px solid #E4E4E4;
box-shadow: 0px 17px 42px rgba(0, 0, 0, 0.12);
border-radius: 8px;
}

.first-column{
display: flex;
flex-direction: column;
}

.details-section{
display: flex;
flex-direction: row;
}

.pick-up{
font-family: 'DM Sans';
font-style: normal;
font-weight: 500;
font-size: 14px;
line-height: 21px;
color: #000000;
margin: 32px 0 0 77px;
}

.pick{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 10px;
line-height: 12px;
color: #777777;
margin-left: 8px;
}

.more-details{
display: flex;
flex-direction: row;
margin: 32px 0 0 21px;
cursor: pointer;
}

.details-text{
font-family: 'Rubik';
font-style: normal;
font-weight: 400;
font-size: 10px;
line-height: 21px;
color: #D9B608;
margin: 0 0 0 0;
}

.gold-dropdown{
width: 6px;
height: 6px;
margin: auto 0 auto 7px;
}

.first-row{
display: flex;
flex-direction: row;
margin: 34px 0 0 31px;
}

.direction-arrows{
height: 15.1px;
width: 16.3px; 
margin: auto 0 auto 0;
}

.from{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 10px;
line-height: 12px;
color: #515151;
margin: auto 0 auto 31px;
}

.locator-img{
height: 14.6px;
width: 11.9px;
margin: auto 0 auto 15px;
}

.locator-text{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 12px;
line-height: 16px;
color: #000000;
margin: auto 0 auto 14px;
}

.second-row{
display: flex;
flex-direction: row;
margin: 17px 0 0 80px;
}

.to{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 10px;
line-height: 12px;
color: #515151;
margin: auto 0 auto 0;
}

.locator-img2{
margin: auto 0 auto 27px;
height: 14.6px;
width: 11.9px;
}

.info-rule{
width: 500px;
border: 1px solid #F3F3F3; 
margin: 24px 0 0 0;
}

.third-row{
display: flex;
flex-direction: row;
margin: 34px 0 0 23px;
}

.profile-icon{
height: 32px;
width: 32px;
margin: auto 0 auto 0;
}

.from2{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 10px;
color: #515151;
margin: auto 0 auto 23px;
}

.profilepic{
width: 24px;
height: 20px;
margin: auto 0 auto 14px; 
border-radius: 50%;
}

.locator-name{
font-family: 'DM Sans';
font-style: normal;
font-weight: 500;
font-size: 12px;
line-height: 16px;
color: #000000;
margin: auto 0 auto 4px;
}

.fourth-row{
display: flex;
flex-direction: row;
margin: 8px 0 0 122.8px;
}

.to2{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 10px;
line-height: 12px;
color: #515151;
margin: auto 0 auto 14px;
}

.phone{
height: 10.2px;
width: 10.2px;
margin: auto 0 auto 0;
}

.number{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 10px;
line-height: 16px;
color: #777777; 
margin: auto 0 auto 11px;
}

.fifth-row{
display: flex;
flex-direction: row;
margin: 8px 0 0 63.8px;
}

.sixth-row{
display: flex;
flex-direction: row;
margin: 8px 0 0 122.8px;
}

.profilepic2{
width: 24px;
height: 20px;
margin: auto 0 auto 26px; 
border-radius: 50%;
}

.seventh-row{
display: flex;
flex-direction: row;
margin: 30px 0 0 31px;
}

.clock{
height: 18.1px;
width: 17px;
margin: 0 0 0 0;
}

.date{
margin: 0 0 0 31px; 
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 10px;
line-height: 16px;
color: #313131;
}

.time{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 10px;
line-height: 16px;
color: #313131; 
margin: 0 0 0 61px; 
}

.package{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 10px;
line-height: 16px;
color: #313131; 
margin: 0 0 0 41px;
white-space: nowrap;
}

.assign-btn2{
width: 192px;
height: 40px;
background: #FFD60A;
border-radius: 8px;
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 14px;
line-height: 24px;
color: #000000;
border: none;
margin: -6px 32px -16px 58px;
}

.eight-row{
display: flex;
flex-direction: row;
margin: 0 0 0 80px;
}

.date1{
font-family: 'DM Sans';
font-style: normal;
font-weight: 500;
font-size: 12px;
line-height: 16px;
color: #030303;
margin: 0 0 0 0;
}

.time1{
font-family: 'DM Sans';
font-style: normal;
font-weight: 500;
font-size: 12px;
line-height: 16px;
color: #030303;
margin: 0 0 0 34px;
}

.package1{
font-family: 'DM Sans';
font-style: normal;
font-weight: 500;
font-size: 12px;
line-height: 16px;
color: #030303;
margin: 0 0 0 33px;
}

.nine-row{
display: flex;
flex-direction: row;
margin: 24px 0 32px 80px;
}

.assign-btn{
width: 192px;
height: 40px;
background: #FFD60A;
border: none;
border-radius: 8px;
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 14px;
line-height: 24px;
color: #000000;
}

.cancel-btn{
width: 192px;
height: 40px;
background: #FFFFFF;
border: 1px solid #CC5500;
border-radius: 8px;
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 14px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 16px;
}

.second-column{
display: flex;
flex-direction: row;
margin: 0 0 0 0;
align-items: center;
}

.columnimg{
width: 533px;
height: 350px;
margin: auto 0 auto 0;
}

.column-img{
width: 465px;
height: 175px;
margin: auto 0 auto 0; 
}
</style>