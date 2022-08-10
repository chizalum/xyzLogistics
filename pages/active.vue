<template>
  <div class="fullscreen">
    <div class="headdata">
      <input
        type="checkbox"
        class="box"
        @click="checkAll()"
        v-model="isCheckAll"
      />
      <p class="headdata1">Tracking number</p>
      <p class="headdata2">Customer name</p>
      <p class="headdata3">Customer number</p>
      <p class="headdata4">Dispatch name</p>
      <p class="headdata5">Vehicle</p>
      <p class="headdata6">Location</p>
      <p class="headdata7">Package size</p>
      <p class="headdata8">Date</p>
    </div>
    <div v-for="(details, index) in packageDetails" :key="index">
      <div class="body-head">
        <input
          type="checkbox"
          class="box1"
          v-bind:value="details"
          v-model="languages"
          @change="updateCheckall()"
        />
        <div @click="showImage(index)" class="body-info">
          <p class="bodydata1">{{ details.trackingNumber }}</p>
          <p class="bodydata2">{{ details.name }}</p>
          <p class="bodydata3">{{ details.phone }}</p>
          <p class="bodydata4">{{ details.dispatchName }}</p>
          <p class="bodydata5">{{ details.vehicle }}</p>
          <p class="bodydata6">{{ details.address }}</p>
          <p class="bodydata7">{{ details.package }}</p>
          <p class="bodydata8">{{ details.date }}</p>
          <img
            src="droparrow.png"
            class="droparrow"
            :class="{ rotate: details.turn }"
          />
        </div>
      </div>
      <div class="viewcontainer" v-show="details.show">
        <div class="first-column">
          <p class="pick-up">Pick-up<span class="pick">(Local)</span></p>
          <div class="first-row">
            <img src="directionarrows.svg" class="direction-arrows" />
            <p class="from">From</p>
            <img src="locator.svg" class="locator-img" />
            <p class="locator-text">
              12 Odutola street, Adaba B/stp, Egbeda, Lagos.
            </p>
          </div>
          <div class="second-row">
            <p class="to">To</p>
            <img src="locator.svg" class="locator-img2" />
            <p class="locator-text">
              12 Odutola street, Adaba B/stp, Egbeda, Lagos.
            </p>
          </div>
          <hr class="info-rule" />
          <div class="third-row">
            <img src="profile-icon.svg" class="profile-icon" />
            <p class="from2">From</p>
            <img src="profilepic.png" class="profilepic" />
            <p class="locator-name">Ajibike Lola</p>
          </div>
          <div class="fourth-row">
            <img src="phone.svg" class="phone" />
            <p class="number">07064783993</p>
          </div>
          <div class="fifth-row">
            <p class="to2">To</p>
            <img src="profilepic.png" class="profilepic2" />
            <p class="locator-name">Ajibike Lola</p>
          </div>
          <div class="sixth-row">
            <img src="phone.svg" class="phone" />
            <p class="number">07064783993</p>
          </div>
          <hr class="info-rule" />
          <div class="seventh-row">
            <img src="clock.svg" class="clock" />
            <p class="date">Date</p>
            <p class="time">Time</p>
            <p class="package">Package Size</p>
          </div>
          <div class="eight-row">
            <p class="date1">12/03/22</p>
            <p class="time1">10am</p>
            <p class="package1">Medium</p>
          </div>
        </div>
        <div class="second-column">
          <img src="orders-img.png" class="column-img" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "active",
  layout: "orders",
  data() {
    return {
      isCheckAll: false,
      languages: [],
      packageDetails: [
        {
          index: 1,
          trackingNumber: "18-6589929",
          name: "Ajibike lola",
          phone: "0806573862587",
          dispatchName: "Yusuf",
          vehicle: "Bike",
          address: "Lekki",
          package: "Small",
          date: "10/2/22",
          img: "orderview.png",
          checked: "false",
          show: "false",
          turn: "false",
        },
        {
          index: 2,
          trackingNumber: "18-6589929",
          name: "Ajibike lola",
          phone: "0806573862587",
          dispatchName: "Yusuf",
          vehicle: "Bike",
          address: "Lekki",
          package: "Small",
          date: "10/2/22",
          img: "orderview.png",
          checked: "false",
          show: "false",
          turn: "false",
        },
        {
          index: 3,
          trackingNumber: "18-6589929",
          name: "Ajibike lola",
          phone: "0806573862587",
          dispatchName: "Yusuf",
          vehicle: "Bike",
          address: "Lekki",
          package: "Small",
          date: "10/2/22",
          img: "orderview.png",
          checked: "false",
          show: "false",
          turn: "false",
        },
        {
          index: 4,
          trackingNumber: "18-6589929",
          name: "Ajibike lola",
          phone: "0806573862587",
          dispatchName: "Yusuf",
          vehicle: "Bike",
          address: "Lekki",
          package: "Small",
          date: "10/2/22",
          img: "orderview.png",
          checked: "false",
          show: "false",
          turn: "false",
        },
        {
          index: 5,
          trackingNumber: "18-6589929",
          name: "Ajibike lola",
          phone: "0806573862587",
          dispatchName: "Yusuf",
          vehicle: "Bike",
          address: "Lekki",
          package: "Small",
          date: "10/2/22",
          img: "orderview.png",
          checked: "false",
          show: "false",
          turn: "false",
        },
        {
          index: 6,
          trackingNumber: "18-6589929",
          name: "Ajibike lola",
          phone: "0806573862587",
          dispatchName: "Yusuf",
          vehicle: "Bike",
          address: "Lekki",
          package: "Small",
          date: "10/2/22",
          img: "orderview.png",
          checked: "false",
          show: "false",
          turn: "false",
        },
        {
          index: 7,
          trackingNumber: "18-6589929",
          name: "Ajibike lola",
          phone: "0806573862587",
          dispatchName: "Yusuf",
          vehicle: "Bike",
          address: "Lekki",
          package: "Small",
          date: "10/2/22",
          img: "orderview.png",
          checked: "false",
          show: "false",
          turn: "false",
        },
        {
          index: 8,
          trackingNumber: "18-6589929",
          name: "Ajibike lola",
          phone: "0806573862587",
          dispatchName: "Yusuf",
          vehicle: "Bike",
          address: "Lekki",
          package: "Small",
          date: "10/2/22",
          img: "orderview.png",
          checked: "false",
          show: "false",
          turn: "false",
        },
        {
          index: 9,
          trackingNumber: "18-6589929",
          name: "Ajibike lola",
          phone: "0806573862587",
          dispatchName: "Yusuf",
          vehicle: "Bike",
          address: "Lekki",
          package: "Small",
          date: "10/2/22",
          img: "orderview.png",
          checked: "false",
          show: "false",
          turn: "false",
        },
        {
          index: 10,
          trackingNumber: "18-6589929",
          name: "Ajibike lola",
          phone: "0806573862587",
          dispatchName: "Yusuf",
          vehicle: "Bike",
          address: "Lekki",
          package: "Small",
          date: "10/2/22",
          img: "orderview.png",
          checked: "false",
          show: "false",
          turn: "false",
        },
      ],
    };
  },
  methods: {
    checkAll: function () {
      this.isCheckAll = !this.isCheckAll;
      this.languages = [];
      if (this.isCheckAll) {
        // Check all
        for (var key in this.packageDetails) {
          this.languages.push(this.packageDetails[key]);
        }
      }
    },
    updateCheckall: function () {
      if (this.languages.length == this.packageDetails.length) {
        this.isCheckAll = true;
      } else {
        this.isCheckAll = false;
      }
    },

    showImage(index) {
      this.packageDetails[index].show = !this.packageDetails[index].show;
      this.packageDetails[index].turn = !this.packageDetails[index].turn;
    },
  },
};
</script>

<style scoped>
.headdata {
  display: flex;
  flex-direction: row;
  margin: 32px 0 0 368px;
  white-space: nowrap;
}

.box {
  margin: 0 0 0 0;
}

.headdata1 {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #cc5500;
  margin: 0 0 0 32px;
}

.headdata2 {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #cc5500;
  margin: 0 0 0 25px;
}

.headdata3 {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #cc5500;
  margin: 0 0 0 27px;
}

.headdata4 {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #cc5500;
  margin: 0 0 0 38px;
}

.headdata5 {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #cc5500;
  margin: 0 0 0 25px;
}

.headdata6 {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #cc5500;
  margin: 0 0 0 32px;
}

.headdata7 {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #cc5500;
  margin: 0 0 0 34px;
}

.headdata8 {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #cc5500;
  margin: 0 0 0 28px;
}

.body-head {
  display: flex;
  flex-direction: row;
  width: 1090px;
  height: 56px;
  background: #ffffff;
  border: 1px solid #e4e4e4;
  margin: 8px 0 0 344px;
  white-space: nowrap;
}

.body-info {
  display: flex;
  flex-direction: row;
}

.body-head:nth-child(1) {
  display: flex;
  flex-direction: row;
  width: 1090px;
  height: 56px;
  background: #ffffff;
  border: 1px solid #e4e4e4;
  margin: 16px 0 0 344px;
}

.box1 {
  margin: auto 0 auto 24px;
}

.bodydata1 {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #000000;
  margin: auto 0 auto 32px;
}

.bodydata2 {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #000000;
  margin: auto 0 auto 58px;
}

.bodydata3 {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #000000;
  margin: auto 0 auto 66px;
}

.bodydata4 {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #000000;
  margin: auto 0 auto 49px;
}

.bodydata5 {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #000000;
  margin: auto 0 auto 93px;
}

.bodydata6 {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #000000;
  margin: auto 0 auto 57px;
}

.bodydata7 {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #000000;
  margin: auto 0 auto 60px;
}

.bodydata8 {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #000000;
  margin: auto 0 auto 84px;
}

.droparrow {
  width: 8px;
  height: 4px;
  margin: auto 0 auto 32px;
}

.viewcontainer {
  margin: 24px 0 0 344px;
  display: flex;
  flex-direction: row;
  height: 430px;
  width: 1057px;
  background: #ffffff;
  border: 1px solid #e4e4e4;
  box-shadow: 0px 17px 42px rgba(0, 0, 0, 0.12);
  border-radius: 8px;
}

.first-column {
  display: flex;
  flex-direction: column;
}

.pick-up {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 21px;
  color: #000000;
  margin: 32px 0 0 77px;
}

.pick {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 10px;
  line-height: 12px;
  color: #777777;
  margin-left: 8px;
}

.rotate {
  transform: rotate(180deg);
}

.first-row {
  display: flex;
  flex-direction: row;
  margin: 34px 0 0 31px;
}

.direction-arrows {
  height: 15.1px;
  width: 16.3px;
  margin: auto 0 auto 0;
}

.from {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 10px;
  line-height: 12px;
  color: #515151;
  margin: auto 0 auto 31px;
}

.locator-img {
  height: 14.6px;
  width: 11.9px;
  margin: auto 0 auto 15px;
}

.locator-text {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 12px;
  line-height: 16px;
  color: #000000;
  margin: auto 0 auto 14px;
}

.second-row {
  display: flex;
  flex-direction: row;
  margin: 17px 0 0 80px;
}

.to {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 10px;
  line-height: 12px;
  color: #515151;
  margin: auto 0 auto 0;
}

.locator-img2 {
  margin: auto 0 auto 27px;
  height: 14.6px;
  width: 11.9px;
}

.info-rule {
  width: 500px;
  border: 1px solid #f3f3f3;
  margin: 24px 0 0 0;
}

.third-row {
  display: flex;
  flex-direction: row;
  margin: 34px 0 0 31px;
}

.profile-icon {
  height: 17px;
  width: 17px;
  margin: auto 0 auto 0;
}

.from2 {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 10px;
  color: #515151;
  margin: auto 0 auto 29px;
}

.profilepic {
  width: 24px;
  height: 20px;
  margin: auto 0 auto 14px;
  border-radius: 50%;
}

.locator-name {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 500;
  font-size: 12px;
  line-height: 16px;
  color: #000000;
  margin: auto 0 auto 4px;
}

.fourth-row {
  display: flex;
  flex-direction: row;
  margin: 8px 0 0 122.8px;
}

.to2 {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 10px;
  line-height: 12px;
  color: #515151;
  margin: auto 0 auto 14px;
}

.phone {
  height: 10.2px;
  width: 10.2px;
  margin: auto 0 auto 0;
}

.number {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 10px;
  line-height: 16px;
  color: #777777;
  margin: auto 0 auto 11px;
}

.fifth-row {
  display: flex;
  flex-direction: row;
  margin: 8px 0 0 63.8px;
}

.sixth-row {
  display: flex;
  flex-direction: row;
  margin: 8px 0 0 122.8px;
}

.profilepic2 {
  width: 24px;
  height: 20px;
  margin: auto 0 auto 26px;
  border-radius: 50%;
}

.seventh-row {
  display: flex;
  flex-direction: row;
  margin: 30px 0 0 31px;
}

.clock {
  height: 18.1px;
  width: 17px;
  margin: 0 0 0 0;
}

.date {
  margin: 0 0 0 31px;
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 10px;
  line-height: 16px;
  color: #313131;
}

.time {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 10px;
  line-height: 16px;
  color: #313131;
  margin: 0 0 0 71px;
}

.package {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 10px;
  line-height: 16px;
  color: #313131;
  margin: 0 0 0 51px;
}

.eight-row {
  display: flex;
  flex-direction: row;
  margin: 0 0 0 80px;
}

.date1 {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 500;
  font-size: 12px;
  line-height: 16px;
  color: #030303;
  margin: 0 0 0 0;
}

.time1 {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 500;
  font-size: 12px;
  line-height: 16px;
  color: #030303;
  margin: 0 0 0 44px;
}

.package1 {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 500;
  font-size: 12px;
  line-height: 16px;
  color: #030303;
  margin: 0 0 0 43px;
}

.second-column {
  display: flex;
  flex-direction: row;
  margin: 0 0 0 0;
  align-items: center;
}

.column-img {
  width: 533px;
  height: 350px;
  margin: auto 0 auto 0;
}

</style>

