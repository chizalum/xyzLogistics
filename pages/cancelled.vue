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
        <div class="body-info" @click="viewModal()">
          <p class="bodydata1">{{ details.trackingNumber }}</p>
          <p class="bodydata2">{{ details.name }}</p>
          <p class="bodydata3">{{ details.phone }}</p>
          <p class="bodydata4">{{ details.dispatchName }}</p>
          <p class="bodydata5">{{ details.vehicle }}</p>
          <p class="bodydata6">{{ details.address }}</p>
          <p class="bodydata7">{{ details.package }}</p>
          <p class="bodydata8">{{ details.date }}</p>
        </div>
      </div>
    </div>
    <cancelledmodal v-if="showModal" @closeModal="offModal" />
  </div>
</template>

<script>
export default {
  name: "cancelled",
  layout: "orders",
  data() {
    return {
      showModal: false,
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

    viewModal() {
      this.showModal = true;
    },
    offModal() {
      this.showModal = false;
      console.log(this.showModal);
    },
  },
};
</script>

<style scoped>
.fullscreen {
  white-space: nowrap;
}

.headdata {
  display: flex;
  flex-direction: row;
  margin: 32px 0 0 368px;
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
</style>