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
            <div class="navitem2" @click="changeOrder()" :class="{ activenav2: activeBar2 }">
              <img :src="orderimage[orderCurrent]" alt="orders" class="ordersimg">
              <nuxt-link to="/" class="orderstext" :class="{ orderstext2: isActive2 }">Orders</nuxt-link>
            </div>
            <div class="orderDD" v-if="show">
              <vr class="verticalrule"></vr>
              <div class="orderview">
                <nuxt-link to="/" @click.native="changeFirst()"  class="orderitems1">
                  Active Orders
                </nuxt-link>
                <nuxt-link to="/" @click.native="changeSecond()" class="orderitems2">
                  Delivered
                </nuxt-link>
                <nuxt-link to="/" @click.native="changeThird()" class="orderitems3">
                   Pending Orders
                </nuxt-link>
                <nuxt-link to="/" @click.native="changeFourth()" class="orderitems4"> 
                  Cancelled
                </nuxt-link>
              </div>
            </div>
        </div>    
        <div class="navitem3" @click="changeAgents()" :class="{ activenav3: activeBar3 }">
          <img :src="agentsimage[agentsCurrent]" alt="agents" class="agentsimg">
          <nuxt-link to="/" class="agentstext" :class="{ agentstext2: isActive3 }">Agents</nuxt-link>
        </div>
        <div>    
            <div class="navitem4" @click="changeVehicles()" :class="{ activenav4: activeBar4 }">
              <img :src="vehiclesimage[vehiclesCurrent]" alt="vehicles" class="vehiclesimg">
              <nuxt-link to="/" class="vehiclestext" :class="{ vehiclestext2: isActive4 }">Vehicles</nuxt-link>
            </div>
            <div class="orderDD" v-if="view">
              <vr class="verticalrule1"></vr>
              <div class="orderview">
                <nuxt-link to="/" @click.native="changeVan()" class="vehicleitems" :class="{vehicleclick3: vehicleActive3}">
                  Vans
                </nuxt-link>
                <nuxt-link to="/" @click.native="changeTruck()" class="vehicleitems" :class="{vehicleclick3: vehicleActive3}">
                  Trucks
                </nuxt-link>
                <nuxt-link to="/" @click.native="changeBike()" class="vehicleitems" :class="{vehicleclick3: vehicleActive3}">
                   Bikes
                </nuxt-link>
              </div>
            </div>  
        </div>    
            <hr class="siderule"> 
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
      isActive1: false,
      isActive2: false,
      isActive3: false,
      isActive4: false,
      isActive5: false,
      activeBar1: true,
      activeBar2: false,
      activeBar3: false,
      activeBar4: false,
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
    this.activeBar2 = false;
    this.activeBar3 = false;
    this.activeBar4 = false;
    this.activeBar5 = false;
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
    this.activeBar2 = !this.activeBar2;
    this.activeBar1 = false;
    this.activeBar3 = false;
    this.activeBar4 = false;
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
    this.activeBar2 = false;
    this.activeBar4 = false;
    this.activeBar5 = false;
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
    this.activeBar4 = !this.activeBar4;
    this.activeBar1 = false;
    this.activeBar3 = false;
    this.activeBar2 = false;
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
    this.activeBar4 = false;
    this.activeBar2 = false;
  },

  changeVan(){
        
  },

  changeTruck(){
        
  },

  changeBike(){
        
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
  margin: 0 0 24px 24px;
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
  background-image: linear-gradient(to right, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
  background:-webkit-linear-gradient(to right, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
}

.activenav2{
  background-image: linear-gradient(to right, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
  background:-webkit-linear-gradient(to right, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
}

.activenav3{
  background-image: linear-gradient(to right, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
  background:-webkit-linear-gradient(to right, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
}

.activenav4{
  background-image: linear-gradient(to right, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
  background:-webkit-linear-gradient(to right, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
}

.activenav5{
  background-image: linear-gradient(to right, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
  background:-webkit-linear-gradient(to right, #D9B608, #D9B608 0%, #FBFBFB, #FBFBFB 5%);
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
  height: 180px;
  background: #C8C8C8;
  margin-left: 65px;
  position: absolute;
}

.verticalrule1{
  width: 2px;
  height: 118px;
  background: #C8C8C8;
  margin-left: 65px;
  position: absolute;
}

.orderview{
  display: flex;
  flex-direction: column;
}

.orderitems1{
  margin: 20px auto 0 110px;
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #666666;
}

.orderitems2{
  margin: 20px auto 0 110px;
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #666666;
}

.orderitems3{
  margin: 20px auto 0 110px;
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #666666;
}

.orderitems4{
  margin: 20px auto 0 110px;
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #666666;
}

.vehicleitems{
  margin: 20px auto 0 110px;
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #666666;
}



.ordersclick{
  width: 215px;
  height: 56px;
  margin-left: 63px;
}

.ordersclick1{
  width: 215px;
  height: 56px;
  margin-left: 63px;
}

.ordersclick2{
  width: 215px;
  height: 56px;
  margin-left: 63px;
}

.ordersclick3{
  width: 215px;
  height: 56px;
  margin-left: 63px;
}

.vehicleclick1{
  width: 215px;
  height: 56px;
  margin-left: 63px;
}

.vehicleclick2{
  width: 215px;
  height: 56px;
  margin-left: 63px;
}

.vehicleclick3{
  width: 215px;
  height: 56px;
  margin-left: 63px;
}
</style>