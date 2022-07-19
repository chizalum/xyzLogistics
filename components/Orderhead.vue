<template>
  <div class="allscreen">
    <h1 class="orders">Orders</h1>
    <h2 class="manage">Manage all your dispatchers, assign orders, and track orders here.</h2>
    <nav class="navbar">
      <router-link to="/activeorders" class="navlink1" :class="{ordersclick1: ordersActive1}" @click.native="changeFirst()">Active Orders</router-link>
      <router-link to="/deliveredorders" class="navlink2" :class="{ordersclick2: ordersActive2}" @click.native="changeSecond()">Delivered</router-link>
      <router-link to="/pendingorders" class="navlink3" :class="{ordersclick3: ordersActive3}" @click.native="changeThird()">Pending Orders</router-link>
      <router-link to="/cancelledorders" class="navlink4" :class="{ordersclick4: ordersActive4}" @click.native="changeFourth()">Cancelled</router-link>
    </nav>
    <div class="indicatorbars">
      <div class="indicatorbar1" :class="{indicatorclick1: ordersActive1}"></div>
      <div class="indicatorbar2" :class="{indicatorclick2: ordersActive2}"></div>
      <div class="indicatorbar3" :class="{indicatorclick3: ordersActive3}"></div>
      <div class="indicatorbar4" :class="{indicatorclick4: ordersActive4}"></div>
    </div>
    <hr class="horizontalrule">
    <div class="infobar">
      <div>
      <input type="search" placeholder="Search" class="searchbar">
      </div>
      <div class="moreinfo">
        <div class="infogroups">
          <p class="infotext">Vehicle</p>
          <img src="droparrow.png" class="droparrow" alt="droparrow">
        </div>
        <div class="infogroups">
          <p class="infotext">Location</p>
          <img src="droparrow.png" class="droparrow" alt="droparrow">
        </div>
        <div class="infogroups">
          <p class="infotext">Package size</p>
          <img src="droparrow.png" class="droparrow" alt="droparrow">
        </div>
        <div class="infogroups">
          <p class="infotext">Date</p>
          <img src="droparrow.png" class="droparrow" alt="droparrow">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Orderhead',

  data() {
    return{
      ordersActive1 : true,
      ordersActive2 : false,
      ordersActive3 : false,
      ordersActive4 : false,
    }
  },

  methods: {
    changeFirst() {
      this.ordersActive1 = true;
      this.ordersActive2 = false;
      this.ordersActive3 = false;
      this.ordersActive4 = false;
    },
    changeSecond() {
      this.ordersActive1 = false;
      this.ordersActive2 = true;
      this.ordersActive3 = false;
      this.ordersActive4 = false;
    },
    changeThird() {
      this.ordersActive1 = false;
      this.ordersActive2 = false;
      this.ordersActive3 = true;
      this.ordersActive4 = false;
    },
    changeFourth() {
      this.ordersActive1 = false;
      this.ordersActive2 = false;
      this.ordersActive3 = false;
      this.ordersActive4 = true;
    },
  }
}
</script>

<style scoped>
.allscreens{
height: 100vh;
width: 100vw;
white-space: nowrap;
}

.orders{
font-family: 'DM Sans';
font-style: normal;
font-weight: 700;
font-size: 25px;
line-height: 40px;
color: #000000;  
margin: 96px 0 0 368px;
}

.manage{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #575757;
margin: 8px 0 0 368px;
}

.navbar{
display: flex;
flex-direction: row;
margin: 32px 0 0 368px;
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

.navlink3{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #777777;  
margin: 0 32px 0 0;
text-decoration: none;
}

.navlink4{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #777777;  
margin: 0 0 0 0;
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
margin: 0 32px 0 2px;
}

.indicatorbar3{
width: 80px;
height: 4px;
min-width: 80px;
min-height: 4px;
border-radius: 8px 8px 0px 0px;  
margin: 0 32px 0 0;
}

.indicatorbar4{
width: 80px;
height: 4px;
min-width: 80px;
min-height: 4px;
border-radius: 8px 8px 0px 0px;  
margin: 0 0 0 4px;
}

.indicatorclick1{
background: #D9B608;
}

.indicatorclick2{
background: #D9B608;
}

.indicatorclick3{
background: #D9B608;
}

.indicatorclick4{
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

.ordersclick3{
font-weight: 700;
color: #000000;
}

.ordersclick4{
font-weight: 700;
color: #000000;
}

.horizontalrule{
width: 1120px;
height: 0px;
border: 1px solid #F3F3F3;
margin: 0 0 0 320px;
}

.infobar{
display: flex;
flex-direction: row;
margin: 32px 0 0 368px;
height: 40px;
}

.searchbar{
width: 590px;
height: 40px;
left: 368px;
top: 272px;
border: 1px solid #E4E4E4;
border-radius: 8px;
margin: 0 32px 0 0;
background: url("");
}

.moreinfo{
display: flex;
flex-direction: row;
width: 452px;
height: 40px;
border: 1px solid #E4E4E4;
border-radius: 8px;
white-space: nowrap;
padding: 0;
}

.infogroups{
display: flex;
flex-direction: row;
margin: 0 36px 0 0;
}

.infogroups:nth-child(1){
margin-left: 32px;
}

.infotext{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 14px;
line-height: 21px;
color: #000000;
margin: auto 12px auto 0;
}

.droparrow{
height: 4px;
width: 8px;
margin: auto 0 auto 0;
}
</style>
