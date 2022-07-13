<template>
  <div>
    <div class="sidebar">
      <img src="xyzlogo.png" alt="logo" class="logo"> 
      <hr class="siderule">
      <nav class="navbar">
        <div>
            <div class="navitems">
              <img src="dashboardActive.png" alt="dashboard" class="dashboardimg">
            </div>
        </div>
        <div>
            <div class="navitems" @click="changeOrder()">
              <img :src="orderimage[orderCurrent]" alt="orders" class="ordersimg">
            </div>
            <div class="orderDD" v-if="show">
              <vr class="verticalrule"></vr>
              <div class="orderview">
                <nuxt-link to="/" class="orderitems" @click="changeFirst()">
                  <img :src="firstorder[firstOrderNo]">
                </nuxt-link>
                <nuxt-link to="/" class="orderitems" @click="changeSecond()">
                  <img :src="secondorder[secondOrderNo]">
                </nuxt-link>
                <nuxt-link to="/" class="orderitems" @click="changeThird()">
                   <img :src="thirdorder[thirdOrderNo]">
                </nuxt-link>
                <nuxt-link to="/" class="orderitems" @click="changeFourth()"> 
                   <img :src="fourthorder[fourthOrderNo]">
                </nuxt-link>
              </div>
            </div>
        </div>
        <div>    
            <div class="navitems" @click="changeAgents()">
              <img :src="agentsimage[agentsCurrent]" alt="agents" :class="{agentsimg2: agentsActive}" class="agentsimg">
            </div>
        </div>
        <div>    
            <div class="navitems" @click="changeVehicles()">
              <img :src="vehiclesimage[vehiclesCurrent]" alt="vehicles" class="vehiclesimg">
            </div>
            <div class="orderDD" v-if="view">
              <vr class="verticalrule1"></vr>
              <div class="orderview">
                <nuxt-link to="/" class="vehicleitems">
                  <img src="Vans.png">
                </nuxt-link>
                <nuxt-link to="/" class="vehicleitems">
                  <img src="Trucks.png">
                </nuxt-link>
                <nuxt-link to="/" class="vehicleitems">
                   <img src="Bikes.png">
                </nuxt-link>
              </div>
            </div>  
        </div>    
            <hr class="siderule">
        <div>    
            <div class="navitems" @click="changeSettings()">
              <img :src="settingsimage[settingsCurrent]" alt="settings" :class="{settingsimg2: settingsActive}" class="settingsimg">
            </div>
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
      orderimage: ['orders.png', 'ordersActive.png'],
      orderCurrent: 0,
      agentsimage: ['agents.png', 'agentsActive.png'],
      agentsCurrent: 0,
      agentsActive: false,
      vehiclesimage: ['vehicles.png', 'vehiclesActive.png'],
      vehiclesCurrent: 0,
      settingsimage: ['settings.png', 'settingsActive.png'],
      settingsCurrent: 0,
      settingssActive: false,
      show: false,
      view: false,
      firstorder: ['Activeorders.png', 'activeOrdersLive.png'],
      firstOrderNo: 0,
      secondorder: ['Delivered.png', 'deliveredLive.png'],
      secondOrderNo: 0,
      thirdorder: ['PendingOrders.png','reqestsLive.png'],
      thirdOrderNo: 0,
      fourthorder: ['Cancelled.png', 'cancelledLive.png'],
      fourthOrderNo: 0,
    }
  },

  methods: {
    changeOrder(){
        if(this.orderCurrent < this.orderimage.length-1){
            this.orderCurrent++
    }else{
           this.orderCurrent= 0
    };
    this.show = !this.show
},

    changeAgents(){
        if(this.agentsCurrent < this.agentsimage.length-1){
            this.agentsCurrent++
    }else{
           this.agentsCurrent= 0
    };
    this.agentsActive = !this.agentsActive;
  },

    changeVehicles(){
        if(this.vehiclesCurrent < this.vehiclesimage.length-1){
            this.vehiclesCurrent++
    }else{
           this.vehiclesCurrent= 0
    };
    this.view = !this.view
  },

   changeSettings(){
        if(this.settingsCurrent < this.settingsimage.length-1){
            this.settingsCurrent++
    }else{
           this.settingsCurrent= 0
    };
    this.settingsActive = !this.settingsActive;
  },
   
   changeFirst(){
        if(this.firstOrderNo < this.firstorder.length-1){
            this.firstOrderNo++
    }else{
           this.firstOrderNo= 0
    };
  },
 },
}
</script>

<style scoped>
.sidebar {
  width: 320px;
  height: 100%;
  background-color: #ffffff;
  position: fixed;
  top: 0;
  left: 0;
  display: flex;
  flex-direction: column;
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

.navitems{
  margin: 27px auto 0 0;
}

.navitems:nth-child(1){
  margin-left: 32px auto 0 0;
}

.navitems:nth-child(4){
  margin: 27px auto 40px 0;
}

.navitems:nth-child(6){
  margin: 40px auto 0 0;
}

.dashboardimg{
  width: 272px;
  height: 64px;
  margin-left: 24px;
}

.ordersimg{
  width: 100px;
  height: 32px;
  margin-left: 50px;
}

.agentsimg{
  width: 100px;
  height: 32px;
  margin-left: 50px;
}

.agentsimg2{
  width: 272px;
  height: 64px;
  margin-left: 24px;
}

.vehiclesimg{
  width: 110px;
  height: 32px;
  margin-left: 50px;
}

.settingsimg{
  width: 111px;
  height: 32px;
  margin-left: 50px;
}

.settingsimg2{
  width: 272px;
  height: 64px;
  margin-left: 24px;
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

.orderitems{
  margin: 20px auto 0 110px;
}

.orderitems:nth-child(1){
  height: 24px;
  width: 102px;
}

.orderitems:nth-child(2){
  height: 24px;
  width: 70px;
}

.orderitems:nth-child(3){
  height: 24px;
  width: 115px;
}

.orderitems:nth-child(4){
  height: 24px;
  width: 74px;
}

.vehicleitems{
  margin: 20px auto 0 110px;
}

.vehicleitems:nth-child(1){
  height: 24px;
  width: 36px;
}

.orderitems:nth-child(2){
  height: 24px;
  width: 48px;
}

.orderitems:nth-child(3){
  height: 24px;
  width: 39px;
}
</style>