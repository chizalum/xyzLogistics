<template>
  <div class="fullwidth">
    <nav class="navbar">
      <router-link to="" class="navlink1" :class="{ordersclick1: ordersActive1}" @click.native="changeFirst()">Users & Roles</router-link>
      <router-link to="" class="navlink2" :class="{ordersclick2: ordersActive2}" @click.native="changeSecond()">Account settings</router-link>
    </nav>
    <div class="indicatorbars">
      <div class="indicatorbar1" :class="{indicatorclick1: ordersActive1}"></div>
      <div class="indicatorbar2" :class="{indicatorclick2: ordersActive2}"></div>
    </div>
    <hr class="horizontalrule">
    <div class="searchbutton">
    <input type="search" class="searchbar" placeholder="Search">
    <button class="button">Add New</button>
    </div>
    <div class="title">
      <p class="name">Name</p>
      <p class="role">Role</p>
      <p class="number">Number</p>
      <p class="mail">Email Address</p>
      <p class="date">Date Added</p>
    </div>
    <div class="data">
      <p class="named">Jide ayomide</p>
      <p class="roled">Admin</p>
      <p class="numbered">08035368293</p>
      <p class="mailed">jidesamuel267@gmail.com</p>
      <p class="dated">12/6/22</p>
      <img src="dots.png" alt="options" class="dots">
    </div>
    <div class="data1">
      <p class="named">Jide ayomide</p>
      <p class="roled">Admin</p>
      <p class="numbered">08035368293</p>
      <p class="mailed">jidesamuel267@gmail.com</p>
      <p class="dated">12/6/22</p>
      <img src="dots.png" alt="options" class="dots">
    </div>
    <div class="data1">
      <p class="named">Jide ayomide</p>
      <p class="roled">Admin</p>
      <p class="numbered">08035368293</p>
      <p class="mailed">jidesamuel267@gmail.com</p>
      <p class="dated">12/6/22</p>
      <img src="dots.png" alt="options" class="dots">
    </div>
    <div class="data1">
      <p class="named">Jide ayomide</p>
      <p class="roled">Admin</p>
      <p class="numbered">08035368293</p>
      <p class="mailed">jidesamuel267@gmail.com</p>
      <p class="dated">12/6/22</p>
      <img src="dots.png" alt="options" class="dots">
    </div>
    <div class="data1">
      <p class="named">Jide ayomide</p>
      <p class="roled">Admin</p>
      <p class="numbered">08035368293</p>
      <p class="mailed">jidesamuel267@gmail.com</p>
      <p class="dated">12/6/22</p>
      <img src="dots.png" alt="options" class="dots">
    </div>
    <div class="data1">
      <p class="named">Jide ayomide</p>
      <p class="roled">Admin</p>
      <p class="numbered">08035368293</p>
      <p class="mailed">jidesamuel267@gmail.com</p>
      <p class="dated">12/6/22</p>
      <img src="dots.png" alt="options" class="dots">
    </div>
    <div class="data1">
      <p class="named">Jide ayomide</p>
      <p class="roled">Admin</p>
      <p class="numbered">08035368293</p>
      <p class="mailed">jidesamuel267@gmail.com</p>
      <p class="dated">12/6/22</p>
      <img src="dots.png" alt="options" class="dots">
    </div>
    <div class="data1">
      <p class="named">Jide ayomide</p>
      <p class="roled">Admin</p>
      <p class="numbered">08035368293</p>
      <p class="mailed">jidesamuel267@gmail.com</p>
      <p class="dated">12/6/22</p>
      <img src="dots.png" alt="options" class="dots">
    </div>
    <div class="data1">
      <p class="named">Jide ayomide</p>
      <p class="roled">Admin</p>
      <p class="numbered">08035368293</p>
      <p class="mailed">jidesamuel267@gmail.com</p>
      <p class="dated">12/6/22</p>
      <img src="dots.png" alt="options" class="dots">
    </div>
    <div class="data1">
      <p class="named">Jide ayomide</p>
      <p class="roled">Admin</p>
      <p class="numbered">08035368293</p>
      <p class="mailed">jidesamuel267@gmail.com</p>
      <p class="dated">12/6/22</p>
      <img src="dots.png" alt="options" class="dots">
    </div>
  </div>
</template>

<script>
export default {
  name: 'settings',
  data() {
    return{
      ordersActive1 : true,
      ordersActive2 : false,
    }
  },

  methods: {
    changeFirst() {
      this.ordersActive1 = true;
      this.ordersActive2 = false;
    },
    changeSecond() {
      this.ordersActive1 = false;
      this.ordersActive2 = true;
    },
  }
}
</script>

<style scoped>
.fullwidth{
height: 100vh;
width: 100vw;
}

.navbar{
display: flex;
flex-direction: row;
margin: 104px 0 0 368px;
white-space: nowrap;
}

.navlink1{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #777777;  
margin: 0 32px 0 0;
text-decoration: none;
}

.navlink2{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #777777;  
margin: 0 32px 0 0;
text-decoration: none;
}

.indicatorbars{
display: flex;
flex-direction: row;
margin: 12px 0 0 368px;
white-space: nowrap;
}

.indicatorbar1{
width: 80px;
height: 4px;
min-width: 80px;
min-height: 4px;
border-radius: 8px 8px 0px 0px;  
margin: 0 32px 0 8px;
}

.indicatorbar2{
width: 80px;
height: 4px;
min-width: 80px;
min-height: 4px;
border-radius: 8px 8px 0px 0px;  
margin: 0 32px 0 15px;
}


.indicatorclick1{
background: #D9B608;
}

.indicatorclick2{
background: #D9B608;
}

.ordersclick1{
font-weight: 700;
color: #000000;
}

.ordersclick2{
font-weight: 700;
color: #000000;
}

.horizontalrule{
width: 1050px;
height: 0px;
left: 320px;
top: 144px;
background: #F3F3F3;
border: 1px solid #F3F3F3; 
margin: 0 0 0 320px;  
}

.searchbutton{
display: flex;
flex-direction: row;
}

.searchbar{
width: 711px;
height: 40px;
left: 368px;
top: 176px;
border: 1px solid #E4E4E4;
border-radius: 8px;   
margin: 32px 0 0 368px;
}

.button{
width: 184px;
height: 40px;
left: 1119px;
top: 176px;
background: #FFD60A;
border-radius: 8px;
border: none;  
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 14px;
line-height: 24px;
color: #000000;
margin: 32px 0 0 40px;
}

.title{
display: flex;
flex-direction: row;
margin: 32px 0 0 368px;
white-space: nowrap;
}

.name{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 0;
}

.role{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 139px;
}

.number{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 83px;
}

.mail{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 80px;
}

.date{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 140px;
}

.data{
width: 1207px;
height: 56px;
background: #FFFFFF; 
margin: 16px 0 0 344px;  
display: flex;
flex-direction: row;
white-space: nowrap;
}

.data1{
width: 1207px;
height: 56px;
background: #FFFFFF; 
margin: 8px 0 0 344px;  
display: flex;
flex-direction: row;
white-space: nowrap;   
}

.named{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #000000;
margin: auto 93px auto 24px;
}

.roled{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #000000;
margin: auto 69px auto 0;
}

.numbered{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #000000;
margin: auto 47px auto 0;
}

.mailed{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #000000;
margin: auto 56px auto 0;
}

.dated{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #000000;
margin: auto 96px auto 0;
}

.dots{
height: 5.12px;
width: 25.60px;
margin: auto 0 auto 0;
}
</style>
