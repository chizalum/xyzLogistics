<template>
  <div class="fullwidth">
    <h1 class="orders">Orders</h1>
    <h2 class="manage">Manage all your dispatchers, assign orders, and track orders here.</h2>
    <nav class="navbar">
      <router-link to="" class="navlink1" :class="{ordersclick1: ordersActive1}" @click.native="changeFirst()">Active Orders</router-link>
      <router-link to="" class="navlink2" :class="{ordersclick2: ordersActive2}" @click.native="changeSecond()">Delivered</router-link>
      <router-link to="" class="navlink3" :class="{ordersclick3: ordersActive3}" @click.native="changeThird()">Pending Orders</router-link>
      <router-link to="" class="navlink4" :class="{ordersclick4: ordersActive4}" @click.native="changeFourth()">Cancelled</router-link>
    </nav>
    <div class="indicatorbars">
      <div class="indicatorbar1" :class="{indicatorclick1: ordersActive1}"></div>
      <div class="indicatorbar2" :class="{indicatorclick2: ordersActive2}"></div>
      <div class="indicatorbar3" :class="{indicatorclick3: ordersActive3}"></div>
      <div class="indicatorbar4" :class="{indicatorclick4: ordersActive4}"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'orders',
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
.fullwidth{
height: 100vh;
width: 100vw;
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
</style>
