<template>
    <div class="fullscreen">
      <div class="headdata">
        <input type="checkbox" class="box" @click='checkAll()' v-model='isCheckAll'>
        <p class="headdata1">Vehicle</p>
        <p class="headdata2">Vehicle Id</p>
        <p class="headdata3">Condition</p>
        <p class="headdata4">Rider</p>
        <p class="headdata5">Status</p>
        <p class="headdata6">Date Assigned</p>
      </div>
      <div v-for="(details, index) in vehicleInfo" :key="index">
      <div class="body-head">
        <input type="checkbox" class="box1" v-bind:value='details' v-model='languages' @change='updateCheckall()'>
        <div class="body-info">
          <img :src="details.img" class="vanimage">
          <p class="bodydata1">{{details.vehicle}}</p>
          <p class="bodydata2">{{details.vehicleId}}</p>
          <p class="bodydata3">{{details.condition}}</p>
          <p class="bodydata4">{{details.rider[number]}}</p>
          <p class="bodydata5"><span class="bodystatus">{{details.status[number]}}</span></p>
          <p class="bodydata6">{{details.dateAssigned}}</p>
          <Button class="assign-btn" @click="assignRider()">{{details.assign[number]}}</Button>
          <vansmodal v-if="showModal" @closeModal="offModal"  />
        </div>
      </div>
    </div>  
    </div>
</template>

<script>
export default {
  name: 'bikes',
  layout: 'vehicles',

data() {
    return {
      isCheckAll: false,
      languages: [],
      showModal: false,
      number: 0,
      vehicleInfo: [
        {
          index: 1,
          vehicle: 'White van',
          vehicleId: 'Rs-46578',
          condition: 'Good',
          rider: ['- -- -','Jamiu olayinde'],
          status: ['Unassigned','Assigned'],
          assign: ['Assign','Unassign'],
          dateAssigned: '17/7/2020',
          img:'bikes.png',
          checked: 'false',
          show: 'false',
        },
        {
          index: 2,
          vehicle: 'White van',
          vehicleId: 'Rs-46578',
          condition: 'Good',
          rider: ['- -- -','Jamiu olayinde'],
          status: ['Unassigned','Assigned'],
          assign: ['Assign','Unassign'],
          dateAssigned: '17/7/2020',
          img:'bikes.png',
          checked: 'false',
          show: 'false',
        },
        {
          index: 3,
          vehicle: 'White van',
          vehicleId: 'Rs-46578',
          condition: 'Good',
          rider: ['- -- -','Jamiu olayinde'],
          status: ['Unassigned','Assigned'],
          assign: ['Assign','Unassign'],
          dateAssigned: '17/7/2020',
          img:'bikes.png',
          checked: 'false',
          show: 'false',
        },
        {
          index: 4,
          vehicle: 'White van',
          vehicleId: 'Rs-46578',
          condition: 'Good',
          rider: ['- -- -','Jamiu olayinde'],
          status: ['Unassigned','Assigned'],
          assign: ['Assign','Unassign'],
          dateAssigned: '17/7/2020',
          img:'bikes.png',
          checked: 'false',
          show: 'false',
        },
        {
          index: 5,
          vehicle: 'White van',
          vehicleId: 'Rs-46578',
          condition: 'Good',
          rider: ['- -- -','Jamiu olayinde'],
          status: ['Unassigned','Assigned'],
          assign: ['Assign','Unassign'],
          dateAssigned: '17/7/2020',
          img:'bikes.png',
          checked: 'false',
          show: 'false',
        },
        {
          index: 6,
          vehicle: 'White van',
          vehicleId: 'Rs-46578',
          condition: 'Good',
          rider: ['- -- -','Jamiu olayinde'],
          status: ['Unassigned','Assigned'],
          assign: ['Assign','Unassign'],
          dateAssigned: '17/7/2020',
          img:'bikes.png',
          checked: 'false',
          show: 'false',
        },
        {
          index: 7,
          vehicle: 'White van',
          vehicleId: 'Rs-46578',
          condition: 'Good',
          rider: ['- -- -', 'Jamiu olayinde'],
          status: ['Unassigned','Assigned'],
          assign: ['Assign','Unassign'],
          dateAssigned: '17/7/2020',
          img:'bikes.png',
          checked: 'false',
          show: 'false',
        },
        {
          index: 8,
          vehicle: 'White van',
          vehicleId: 'Rs-46578',
          condition: 'Good',
          rider: ['- -- -','Jamiu olayinde'],
          status: ['Unassigned','Assigned'],
          assign: ['Assign','Unassign'],
          dateAssigned: '17/7/2020',
          img:'bikes.png',
          checked: 'false',
          show: 'false',
        },
        {
          index: 9,
          vehicle: 'White van',
          vehicleId: 'Rs-46578',
          condition: 'Good',
          rider: ['- -- -','Jamiu olayinde'],
          status: ['Unassigned','Assigned'],
          assign: ['Assign','Unassign'],
          dateAssigned: '17/7/2020',
          img:'bikes.png',
          checked: 'false',
          show: 'false',
        },
        {
          index: 10,
          vehicle: 'White van',
          vehicleId: 'Rs-46578',
          condition: 'Good',
          rider: ['- -- -','Jamiu olayinde'],
          status: ['Unassigned','Assigned'],
          assign: ['Assign','Unassign'],
          dateAssigned: '17/7/2020',
          img:'bikes.png',
          checked: 'false',
          show: 'false',
        }
      ]
    }
},

methods: {
    checkAll: function(){
      this.isCheckAll = !this.isCheckAll;
      this.languages = [];
      if(this.isCheckAll){ // Check all
        for (var key in this.vehicleInfo) {
          this.languages.push(this.vehicleInfo[key]);
        }
      }
    },
    updateCheckall: function(){
      if(this.languages.length == this.vehicleInfo.length){

         this.isCheckAll = true;
      }else{
         this.isCheckAll = false;
      }
    },

    offModal() {
          this.showModal = false
          console.log(this.showModal)
        },

     assignRider() {
      this.showModal = true
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
margin: 0 99px 0 0;
}

.headdata1{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 0;
}

.headdata2{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 64px;
}

.headdata3{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 45px;
}

.headdata4{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 34px;
}

.headdata5{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 98px;
}

.headdata6{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 112px;
}


.body-head{
display: flex;
flex-direction: row;
width: 1090px;
height: 56px;
background: #FFFFFF;
border: 1px solid #E4E4E4;
margin: 8px 0 0 344px;
}

.body-info{
display: flex;
flex-direction: row; 
}

.body-head:nth-child(1){
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
margin: auto 0 auto 45px;
}

.bodydata2{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #000000;
margin: auto 0 auto 45px;
}

.bodydata3{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #000000;
margin: auto 0 auto 45px;
}

.bodydata4{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #000000;
margin: auto 0 auto 64px;
height: 24px;
width: 111px;
border-radius: 25%;
}

.bodydata5{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #000000;
margin: auto 0 auto 24px;
display: flex;
width: 106px;
height: 32px;
background: #FFC6C6;
border-radius: 64px
}

.bodystatus{
margin: auto auto auto auto;
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

.vanimage{
margin: auto 0 auto 16px;
width: 37px;
height: 18px;
}

.assign-btn{
width: 103px;
height: 32px;
background: #FFD60A;
border-radius: 8px;
border: none;
margin: auto 0 auto 78px;
}
</style>