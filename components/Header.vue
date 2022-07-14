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
                <nuxt-link to="/" @click.native="changeFirst()">
                  <img :src="firstorder[firstOrderNo]" :class="{ordersclick: ordersActive}" class="orderitems1">
                </nuxt-link>
                <nuxt-link to="/" @click.native="changeSecond()">
                  <img :src="secondorder[secondOrderNo]" :class="{ordersclick1: ordersActive1}" class="orderitems2">
                </nuxt-link>
                <nuxt-link to="/" @click.native="changeThird()">
                   <img :src="thirdorder[thirdOrderNo]" :class="{ordersclick2: ordersActive2}" class="orderitems3">
                </nuxt-link>
                <nuxt-link to="/" @click.native="changeFourth()"> 
                   <img :src="fourthorder[fourthOrderNo]" :class="{ordersclick3: ordersActive3}" class="orderitems4">
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
                <nuxt-link to="/" @click.native="changeVan()">
                  <img :src="firstvehicle[firstVehicleNo]" class="vehicleitems" :class="{vehicleclick1: vehicleActive1}">
                </nuxt-link>
                <nuxt-link to="/" @click.native="changeTruck()">
                  <img :src="secondvehicle[secondVehicleNo]" class="vehicleitems" :class="{vehicleclick2: vehicleActive2}">
                </nuxt-link>
                <nuxt-link to="/" @click.native="changeBike()">
                   <img :src="thirdvehicle[thirdVehicleNo]" class="vehicleitems" :class="{vehicleclick3: vehicleActive3}">
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
      settingsActive: false,
      show: false,
      view: false,
      firstorder: ['Activeorders.png', 'activeOrdersLive.png'],
      firstOrderNo: 0,
      secondorder: ['Delivered.png', 'deliveredLive.png'],
      secondOrderNo: 0,
      thirdorder: ['PendingOrders.png','requestsLive.png'],
      thirdOrderNo: 0,
      fourthorder: ['Cancelled.png', 'cancelledLive.png'],
      fourthOrderNo: 0,
      ordersActive: false,
      ordersActive1: false,
      ordersActive2: false,
      ordersActive3: false,
      firstvehicle: ['Vans.png', 'vansActive.png'],
      firstVehicleNo: 0,
      secondvehicle: ['Trucks.png', 'trucksActive.png'],
      secondVehicleNo: 0,
      thirdvehicle: ['Bikes.png', 'bikesActive.png'],
      thirdVehicleNo: 0,
      vehicleActive1: false,
      vehicleActive2: false,
      vehicleActive3: false,
    }
  },

  methods: {
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
    this.agentsCurrent= 0;
    this.vehiclesCurrent= 0;
    this.settingsCurrent= 0
},

    changeAgents(){
        if(this.agentsCurrent < this.agentsimage.length-1){
            this.agentsCurrent++
    }else{
           this.agentsCurrent= 0
    };
    this.agentsActive = !this.agentsActive;
    this.settingsActive = false;
    this.show = false;
    this.view = false;
    this.orderCurrent= 0;
    this.vehiclesCurrent= 0;
    this.settingsCurrent= 0
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
    this.agentsCurrent= 0;
    this.orderCurrent= 0;
    this.settingsCurrent= 0
  },

   changeSettings(){
        if(this.settingsCurrent < this.settingsimage.length-1){
            this.settingsCurrent++
    }else{
           this.settingsCurrent= 0
    };
    this.settingsActive = !this.settingsActive;
    this.show = false;
    this.view = false;
    this.agentsActive = false;
    this.agentsCurrent= 0;
    this.vehiclesCurrent= 0;
    this.orderCurrent= 0
  },
   
   changeFirst(){
        if(this.firstOrderNo < this.firstorder.length-1){
            this.firstOrderNo++
    }else{
           this.firstOrderNo= 0
    };
    this.ordersActive = !this.ordersActive;
    this.ordersActive1 = false;
    this.ordersActive2 = false;
    this.ordersActive3 = false;
    this.secondOrderNo = 0;
    this.thirdOrderNo = 0;
    this.fourthOrderNo = 0;
  },

  changeSecond(){
        if(this.secondOrderNo < this.secondorder.length-1){
            this.secondOrderNo++
    }else{
           this.secondOrderNo= 0
    };
    this.ordersActive1 = !this.ordersActive1;
    this.ordersActive = false;
    this.ordersActive2 = false;
    this.ordersActive3 = false;
    this.firstOrderNo = 0;
    this.thirdOrderNo = 0;
    this.fourthOrderNo = 0;
  },

  changeThird(){
        if(this.thirdOrderNo < this.thirdorder.length-1){
            this.thirdOrderNo++
    }else{
           this.thirdOrderNo= 0
    };
    this.ordersActive2 = !this.ordersActive2;
    this.ordersActive1 = false;
    this.ordersActive = false;
    this.ordersActive3 = false;
    this.firstOrderNo = 0;
    this.secondOrderNo = 0;
    this.fourthOrderNo = 0;
  },

  changeFourth(){
        if(this.fourthOrderNo < this.fourthorder.length-1){
            this.fourthOrderNo++
    }else{
           this.fourthOrderNo= 0
    };
    this.ordersActive3 = !this.ordersActive3;
    this.ordersActive1 = false;
    this.ordersActive2 = false;
    this.ordersActive = false;
    this.secondOrderNo = 0;
    this.firstOrderNo = 0;
    this.thirdOrderNo = 0;
  },

  changeVan(){
        if(this.firstVehicleNo < this.firstvehicle.length-1){
            this.firstVehicleNo++
    }else{
           this.firstVehicleNo= 0
    };
    this.vehicleActive1 = !this.vehicleActive1;
    this.vehicleActive2 = false;
    this.vehicleActive3 = false;
    this.secondVehicleNo = 0;
    this.thirdVehicleNo = 0;
  },

  changeTruck(){
        if(this.secondVehicleNo < this.secondvehicle.length-1){
            this.secondVehicleNo++
    }else{
           this.secondVehicleNo= 0
    };
    this.vehicleActive2 = !this.vehicleActive2;
    this.vehicleActive1 = false;
    this.vehicleActive3 = false;
    this.firstVehicleNo = 0;
    this.thirdVehicleNo = 0;
  },

  changeBike(){
        if(this.thirdVehicleNo < this.thirdvehicle.length-1){
            this.thirdVehicleNo++
    }else{
           this.thirdVehicleNo= 0
    };
    this.vehicleActive3 = !this.vehicleActive3;
    this.vehicleActive2 = false;
    this.vehicleActive1 = false;
    this.secondVehicleNo = 0;
    this.firstVehicleNo = 0;
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

.orderitems1{
  margin: 20px auto 0 110px;
}

.orderitems2{
  margin: 20px auto 0 110px;
}

.orderitems3{
  margin: 20px auto 0 110px;
}

.orderitems4{
  margin: 20px auto 0 110px;
}

.vehicleitems{
  margin: 20px auto 0 110px;
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