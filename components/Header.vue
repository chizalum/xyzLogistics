<template>
  <div>
    <div class="sidebar">
      <img src="xyzlogo.png" alt="logo" class="logo"> 
      <hr class="siderule">
      <nav class="navbar">
        <div class="navitem1" @click="changeDash()" :class="{ activenav1: activeBar1 }">
          <img :src="dashimage[dashCurrent]" alt="dashboard" class="dashboardimg">
          <nuxt-link to="/" class="dashboardtext" :class="{ dashboardtext2: isActive1 }">Dashboard</nuxt-link>
        </div>
        <div>
            <div class="navitem2" @click="changeOrder()">
              <img :src="orderimage[orderCurrent]" alt="orders" class="ordersimg">
              <nuxt-link to="/" class="orderstext" :class="{ orderstext2: isActive2 }">Orders</nuxt-link>
            </div>
            <div class="orderDD" v-if="show">
              <vr class="verticalrule"></vr>
              <div class="orderview">
                <nuxt-link to="/" @click.native="changeFirst()"  class="orderitems1" :class="{ordersclick1: ordersActive1}">
                  <span class="vtext">Active Orders</span>
                </nuxt-link>
                <nuxt-link to="/" @click.native="changeSecond()" class="orderitems2" :class="{ordersclick2: ordersActive2}">
                  <span class="vtext">Delivered</span>
                </nuxt-link>
                <nuxt-link to="/" @click.native="changeThird()" class="orderitems3" :class="{ordersclick3: ordersActive3}">
                   <span class="vtext">Pending Orders</span>
                </nuxt-link>
                <nuxt-link to="/" @click.native="changeFourth()" class="orderitems4" :class="{ordersclick4: ordersActive4}"> 
                  <span class="vtext">Cancelled</span>
                </nuxt-link>
              </div>
            </div>
        </div>    
        <div class="navitem3" @click="changeAgents()" :class="{ activenav3: activeBar3 }">
          <img :src="agentsimage[agentsCurrent]" alt="agents" class="agentsimg">
          <nuxt-link to="/" class="agentstext" :class="{ agentstext2: isActive3 }">Agents</nuxt-link>
        </div>
        <div>    
            <div class="navitem4" @click="changeVehicles()">
              <img :src="vehiclesimage[vehiclesCurrent]" alt="vehicles" class="vehiclesimg">
              <nuxt-link to="/" class="vehiclestext" :class="{ vehiclestext2: isActive4 }">Vehicles</nuxt-link>
            </div>
            <div class="orderDD" v-if="view">
              <vr class="verticalrule1"></vr>
              <div class="orderview">
                <nuxt-link to="/" @click.native="changeVan()" class="vehicleitem1" :class="{vehicleclick1: vehicleActive1}">
                  <span class="vtext">Vans</span>
                </nuxt-link>
                <nuxt-link to="/" @click.native="changeTruck()" class="vehicleitem2" :class="{vehicleclick2: vehicleActive2}">
                  <span class="vtext">Trucks</span>
                </nuxt-link>
                <nuxt-link to="/" @click.native="changeBike()" class="vehicleitem3" :class="{vehicleclick3: vehicleActive3}">
                   <span class="vtext">Bikes</span>
                </nuxt-link>
              </div>
            </div>  
        </div>    
            <hr class="siderule1"> 
        <div class="navitem5" @click="changeSettings()" :class="{ activenav5: activeBar5 }">
           <img :src="settingsimage[settingsCurrent]" alt="settings" class="settingsimg">
           <nuxt-link to="/" class="settingstext" :class="{ settingstext2: isActive5 }">Settings</nuxt-link>
        </div>
      </nav>
   </div>
  </div>
</template>

<script>
export default {
  name: 'Header',

  data(){
    return {
      dashimage: ['dashActive.png', 'dashboard.png'],
      dashCurrent: 0,
      orderimage: ['orders.png', 'ordersActive.png'],
      orderCurrent: 0,
      agentsimage: ['agents.png', 'agentsActive.png'],
      agentsCurrent: 0,
      agentsActive: false,
      vehiclesimage: ['vehicles.png', 'vehiclesActive.png'],
      vehiclesCurrent: 0,
      settingsimage: ['settings.png', 'settingsActive.png'],
      settingsCurrent: 0,
      settingsActive: false,
      show: false,
      view: false,
      vehicleActive1: false,
      vehicleActive2: false,
      vehicleActive3: false,
      ordersActive1: false,
      ordersActive2: false,
      ordersActive3: false,
      ordersActive4: false,
      isActive1: false,
      isActive2: false,
      isActive3: false,
      isActive4: false,
      isActive5: false,
      activeBar1: true,
      activeBar3: false,
      activeBar5: false,
    }
  },

  methods: {
    changeDash(){
    this.dashCurrent= 0;
    this.settingsActive = false;
    this.agentsActive = false;
    this.view = false;
    this.show = false;
    this.agentsCurrent = 0;
    this.vehiclesCurrent = 0;
    this.settingsCurrent = 0;
    this.orderCurrent = 0;
    this.isActive1 = false;
    this.isActive2 = false;
    this.isActive3 = false;
    this.isActive4 = false;
    this.isActive5 = false;
    this.activeBar1 = true;
    this.activeBar3 = false;
    this.activeBar5 = false;
    this.closeSub();
},

    changeOrder(){
        if(this.orderCurrent < this.orderimage.length-1){
            this.orderCurrent++
    }else{
           this.orderCurrent= 0
    };
    this.settingsActive = false;
    this.agentsActive = false;
    this.view = false;
    this.show = !this.show;
    this.dashCurrent= 1;
    this.agentsCurrent = 0;
    this.vehiclesCurrent = 0;
    this.settingsCurrent = 0;
    this.isActive2 = !this.isActive2;
    this.isActive1 = true;
    this.isActive3 = false;
    this.isActive4 = false;
    this.isActive5 = false;
    this.activeBar1 = false;
    this.activeBar3 = false;
    this.activeBar5 = false;
},

    changeAgents(){
    this.agentsCurrent= 1;
    this.settingsActive = false;
    this.agentsActive = false;
    this.show = false;
    this.view = false;
    this.dashCurrent= 1;
    this.vehiclesCurrent = 0;
    this.orderCurrent = 0;
    this.settingsCurrent = 0;
    this.isActive3 = true;
    this.isActive1 = true;
    this.isActive2 = false;
    this.isActive4 = false;
    this.isActive5 = false;
    this.activeBar3 = true;
    this.activeBar1 = false;
    this.activeBar5 = false;
    this.closeSub();
  },

    changeVehicles(){
        if(this.vehiclesCurrent < this.vehiclesimage.length-1){
            this.vehiclesCurrent++
    }else{
           this.vehiclesCurrent= 0
    };
    this.settingsActive = false;
    this.agentsActive = false;
    this.show = false;
    this.view = !this.view;
    this.dashCurrent= 1;
    this.agentsCurrent = 0;
    this.orderCurrent = 0;
    this.settingsCurrent = 0;
    this.isActive4 = !this.isActive4;
    this.isActive1 = true;
    this.isActive2 = false;
    this.isActive3 = false;
    this.isActive5 = false;
    this.activeBar1 = false;
    this.activeBar3 = false;
    this.activeBar5 = false;
  },

   changeSettings(){
    this.settingsCurrent= 1;
    this.settingsActive = !this.settingsActive;
    this.show = false;
    this.view = false;
    this.agentsActive = false;
    this.dashCurrent= 1;
    this.agentsCurrent = 0;
    this.vehiclesCurrent = 0;
    this.orderCurrent = 0;
    this.isActive5 = true;
    this.isActive1 = true;
    this.isActive2 = false;
    this.isActive3 = false;
    this.isActive4 = false;
    this.activeBar5 = true;
    this.activeBar1 = false;
    this.activeBar3 = false;
    this.closeSub();
  },

  changeVan(){
    this.vehicleActive1 = true;
    this.vehicleActive2 = false;
    this.vehicleActive3 = false;
    this.ordersActive1 = false;
    this.ordersActive2 = false;
    this.ordersActive3 = false;
    this.ordersActive4 = false;
  },

  changeTruck(){
    this.vehicleActive1 = false;
    this.vehicleActive2 = true;
    this.vehicleActive3 = false;
    this.ordersActive1 = false;
    this.ordersActive2 = false;
    this.ordersActive3 = false;
    this.ordersActive4 = false;    
  },

  changeBike(){
    this.vehicleActive1 = false;
    this.vehicleActive2 = false;
    this.vehicleActive3 = true;  
    this.ordersActive1 = false;
    this.ordersActive2 = false;
    this.ordersActive3 = false;
    this.ordersActive4 = false;  
  },

  changeFirst(){
    this.ordersActive1 = true;
    this.ordersActive2 = false;
    this.ordersActive3 = false;
    this.ordersActive4 = false;
    this.vehicleActive1 = false;
    this.vehicleActive2 = false;
    this.vehicleActive3 = false;
  },

  changeSecond(){
    this.ordersActive1 = false;
    this.ordersActive2 = true;
    this.ordersActive3 = false;
    this.ordersActive4 = false;
    this.vehicleActive1 = false;
    this.vehicleActive2 = false;
    this.vehicleActive3 = false;
  },

  changeThird(){
    this.ordersActive1 = false;
    this.ordersActive2 = false;
    this.ordersActive3 = true;
    this.ordersActive4 = false;
    this.vehicleActive1 = false;
    this.vehicleActive2 = false;
    this.vehicleActive3 = false;
  },

  changeFourth(){
    this.ordersActive1 = false;
    this.ordersActive2 = false;
    this.ordersActive3 = false;
    this.ordersActive4 = true;
    this.vehicleActive1 = false;
    this.vehicleActive2 = false;
    this.vehicleActive3 = false;
  },

  closeSub(){
    this.ordersActive1 = false;
    this.ordersActive2 = false;
    this.ordersActive3 = false;
    this.ordersActive4 = false;
    this.vehicleActive1 = false;
    this.vehicleActive2 = false;
    this.vehicleActive3 = false;
  },
 },
}
</script>

<style scoped>
.sidebar {
  width: 320px;
  height: 100%;
  background-color: #ffffff;
  top: 0;
  left: 0;
  display: flex;
  flex-direction: column;
  position: absolute;
  box-shadow: 0px 6px 18px 0px #0000000A;
}

.logo{
  width: 172.17px;
  height: 32px;
  margin-top: 48px;
  margin-left: 48px;
  margin-bottom: 48px;
}

.siderule{
width: 100%;
color: #f3f3f3;
border: 1px solid #F3F3F3;
}

.siderule1{
width: 100%;
color: #f3f3f3;
border: 1px solid #F3F3F3;
margin-top: 26px;
}

.navbar{
  display: flex;
  flex-direction: column;
}

.navitem1{
  margin: 32px 0 0 24px;
  display: flex;
  flex-direction: row;
  background: #FFFFFF;
  width: 272px;
  height: 64px;
}

.navitem2{
  margin: 0 0 0 24px;
  display: flex;
  flex-direction: row;
  background: #FFFFFF;
  width: 272px;
  height: 64px;
}

.navitem3{
  margin: 0 0 0 24px;
  display: flex;
  flex-direction: row;
  background: #FFFFFF;

  width: 272px;
  height: 64px;
}


.navitem4{
  margin: 0 0 0 24px;
  display: flex;
  flex-direction: row;
  background: #FFFFFF;
  width: 272px;
  height: 64px;
}


.navitem5{
  margin: 24px 0 0 24px;
  display: flex;
  flex-direction: row;
  background: #FFFFFF;
  width: 272px;
  height: 64px;
}

.activenav1{
  background-image: linear-gradient(0deg, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
  background:-webkit-linear-gradient(0deg, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
}

.activenav3{
  background-image: linear-gradient(0deg, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
  background:-webkit-linear-gradient(0deg, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
}

.activenav5{
  background-image: linear-gradient(0deg, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
  background:-webkit-linear-gradient(0deg, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
}
.dashboardimg{
  width: 25px;
  height: 21.49px;
  margin: auto 0 auto 29px;
}

.dashboardtext{
font-family: 'DM Sans';
font-style: normal;
font-weight: 500;
font-size: 16px;
line-height: 24px;
color: #000000;
margin: auto auto auto 21px;
text-decoration: none;
}

.dashboardtext2{
  font-weight: 500;
  color: #666666;
}

.ordersimg{
  width: 25px;
  height: 23.04px;
  margin: auto 0 auto 27px;
}

.orderstext{
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #666666;
  margin: auto auto auto 21px;
  text-decoration: none;
}

.orderstext2{
  font-weight: 500;
  color: #000000;
}

.agentstext{
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #666666;
  margin: auto auto auto 21px;
  text-decoration: none;
}

.agentstext2{
  font-weight: 500;
  color: #000000;
}

.agentsimg{
  width: 25px;
  height: 25.6px;
  margin: auto 0 auto 29px;
}

.vehiclestext{
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #666666;
  margin: auto auto auto 21px;
  text-decoration: none;
}

.vehiclestext2{
  font-weight: 500;
  color: #000000;
}

.vehiclesimg{
  width: 25px;
  height: 20.8px;
  margin: auto 0 auto 29px;
}

.settingstext{
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #666666;
  margin: auto auto auto 21px;
  text-decoration: none;
}

.settingstext2{
  font-weight: 500;
  color: #000000;
}

.settingsimg{
  width: 25px;
  height: 25.6px;
  margin: auto 0 auto 29px;
}

.orderDD{
  display: flex;
  flex-direction: row;
}

.verticalrule{
  width: 2px;
  height: 220px;
  background: #C8C8C8;
  margin-left: 65px;
  position: absolute;
}

.verticalrule1{
  width: 2px;
  height: 169px;
  background: #C8C8C8;
  margin-left: 65px;
  position: absolute;
}

.orderview{
  display: flex;
  flex-direction: column;
}

.orderitems1{
  margin: 0 auto 0 64px;
  text-decoration: none;
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 56px;
  color: #666666;
  width: 215px;
  height: 56px;
}

.orderitems2{
  margin: 0 auto 0 64px;
  text-decoration: none;
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 56px;
  color: #666666;
  width: 215px;
  height: 56px;
}

.orderitems3{
  margin: 0 auto 0 64px;
  text-decoration: none;
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 56px;
  color: #666666;
  width: 215px;
  height: 56px;
}

.orderitems4{
  margin: 0 auto 0 64px;
  text-decoration: none;
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 56px;
  color: #666666;
  width: 215px;
  height: 56px;
}

.vehicleitem1{
  margin: 0 auto 0 64px;
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 56px;
  color: #666666;
  background: #FFFFFF;
  width: 215px;
  height: 56px;
  text-decoration: none;
}

.vehicleitem2{
  margin: 0 auto 0 64px;
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 56px;
  color: #666666;
  background: #FFFFFF;
  width: 215px;
  height: 56px;
  text-decoration: none;
}

.vehicleitem3{
  margin: 0 auto 0 64px;
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 56px;
  color: #666666;
  background: #FFFFFF;
  width: 215px;
  height: 56px;
  text-decoration: none;
}

.vtext{
  margin: auto 0 auto 32px;
}

.ordersclick1{
  background-image: linear-gradient(0deg, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
  background:-webkit-linear-gradient(0deg, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
  color: #000000;
}

.ordersclick2{
  background-image: linear-gradient(0deg, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
  background:-webkit-linear-gradient(0deg, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
  color: #000000;
}

.ordersclick3{
  background-image: linear-gradient(0deg, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
  background:-webkit-linear-gradient(0deg, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
  color: #000000;
}

.ordersclick4{
  background-image: linear-gradient(0deg, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
  background:-webkit-linear-gradient(0deg, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
  color: #000000;
}

.vehicleclick1{
  background-image: linear-gradient(0deg, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
  background:-webkit-linear-gradient(0deg, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
  color: #000000;
}

.vehicleclick2{
  background-image: linear-gradient(0deg, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
  background:-webkit-linear-gradient(0deg, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
  color: #000000;
}

.vehicleclick3{
  background-image: linear-gradient(0deg, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
  background:-webkit-linear-gradient(0deg, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
  color: #000000;
}
</style>