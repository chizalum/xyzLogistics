<template>
  <div>
    <div class="topbar">
      <img src="bell.svg" alt="bell" class="bell" />
      <h1 class="name">David Odu</h1>
      <img src="online.svg" alt="online" class="online" />
    </div>
    <div class="sidebar">
      <div class="logo-container">
        <img src="xyzlogo.svg" alt="logo" class="logo" />
        <p class="xyz-text">Xyz Logistics</p>
      </div>
      <hr class="siderule" />
      <nav class="navbar">
        <div @click="iconView()">
          <nuxt-link to="/dashboard" class="navitem1"
            ><img
              :src="dashimage[dashCurrent]"
              alt="dashboard"
              class="dashboardimg"
            />Dashboard</nuxt-link
          >
        </div>
        <div @mouseover="startHover()" @mouseleave="stopHover()">
          <div class="navitem2">
            <img
              :src="orderimage[orderCurrent]"
              alt="orders"
              class="ordersimg"
              @click="changeOrder()"
            />
            <p class="orderstext" @click="changeOrder()">Orders</p>
          </div>
          <div class="orderDD" v-if="show">
            <vr class="verticalrule"></vr>
            <div class="orderview">
              <nuxt-link
                to="/active"
                @click.native="iconView()"
                class="orderitems1"
              >
                <span class="vtext">Active Orders</span>
              </nuxt-link>
              <nuxt-link
                to="/delivered"
                @click.native="iconView()"
                class="orderitems2"
              >
                <span class="vtext">Delivered</span>
              </nuxt-link>
              <nuxt-link
                to="/pending"
                @click.native="iconView()"
                class="orderitems3"
              >
                <span class="vtext">Pending Orders</span>
              </nuxt-link>
              <nuxt-link
                to="/cancelled"
                @click.native="iconView()"
                class="orderitems4"
              >
                <span class="vtext">Cancelled</span>
              </nuxt-link>
            </div>
          </div>
        </div>
        <div @click="iconView()">
          <nuxt-link to="/agents" class="navitem3"
            ><img
              :src="agentsimage[agentsCurrent]"
              alt="agents"
              class="agentsimg"
            />Agents</nuxt-link
          >
        </div>
        <div
          @mouseover="startHoverVehicles()"
          @mouseleave="stopHoverVehicles()"
        >
          <div class="navitem4">
            <img
              :src="vehiclesimage[vehiclesCurrent]"
              alt="vehicles"
              class="vehiclesimg"
              @click="changeVehicles()"
            />
            <p class="vehiclestext" @click="changeVehicles()">Vehicles</p>
          </div>
          <div class="orderDD" v-if="view">
            <vr class="verticalrule1"></vr>
            <div class="orderview">
              <nuxt-link
                to="/vans"
                @click.native="iconView()"
                class="vehicleitem1"
              >
                <span class="vtext">Vans</span>
              </nuxt-link>
              <nuxt-link
                to="/trucks"
                @click.native="iconView()"
                class="vehicleitem2"
              >
                <span class="vtext">Trucks</span>
              </nuxt-link>
              <nuxt-link
                to="/bikes"
                @click.native="iconView()"
                class="vehicleitem3"
              >
                <span class="vtext">Bikes</span>
              </nuxt-link>
            </div>
          </div>
        </div>
        <hr class="siderule1" />
        <div @click="iconView()">
          <nuxt-link to="/settings" class="navitem5"
            ><img
              :src="settingsimage[settingsCurrent]"
              alt="settings"
              class="settingsimg"
            />Settings</nuxt-link
          >
        </div>
      </nav>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header",

  data() {
    return {
      dashimage: ["dashboard.svg", "dashActive.svg"],
      dashCurrent: 0,
      orderimage: ["orders.svg", "ordersActive.svg"],
      orderCurrent: 0,
      agentsimage: ["agents.svg", "agentsActive.svg"],
      agentsCurrent: 0,
      agentsActive: false,
      vehiclesimage: ["vehicles.svg", "vehiclesActive.svg"],
      vehiclesCurrent: 0,
      settingsimage: ["settings.svg", "settingsActive.svg"],
      settingsCurrent: 0,
      settingsActive: false,
      show: false,
      view: false,
    };
  },

  created() {
    this.iconView();
  },

  methods: {
    iconView() {
      if (this.$route.name.includes("dashboard")) {
        this.dashCurrent = 1;
        this.agentsCurrent = 0;
        this.vehiclesCurrent = 0;
        this.orderCurrent = 0;
        this.settingsCurrent = 0;
        this.view = false;
        this.show = false;
      } else if (this.$route.name.includes("agents")) {
        this.agentsCurrent = 1;
        this.settingsActive = false;
        this.agentsActive = false;
        this.show = false;
        this.view = false;
        this.dashCurrent = 0;
        this.vehiclesCurrent = 0;
        this.orderCurrent = 0;
        this.settingsCurrent = 0;
      } else if (this.$route.name.includes("settings")) {
        this.settingsCurrent = 1;
        this.settingsActive = !this.settingsActive;
        this.show = false;
        this.view = false;
        this.agentsActive = false;
        this.dashCurrent = 0;
        this.agentsCurrent = 0;
        this.vehiclesCurrent = 0;
        this.orderCurrent = 0;
      } else if (this.$route.name.includes("active")) {
        this.show = true;
        this.orderCurrent = 1;
      } else if (this.$route.name.includes("delivered")) {
        this.show = true;
        this.orderCurrent = 1;
      } else if (this.$route.name.includes("pending")) {
        this.show = true;
        this.orderCurrent = 1;
      } else if (this.$route.name.includes("cancelled")) {
        this.show = true;
        this.orderCurrent = 1;
      } else if (this.$route.name.includes("vans")) {
        this.view = true;
        this.vehiclesCurrent = 1;
      } else if (this.$route.name.includes("trucks")) {
        this.view = true;
        this.vehiclesCurrent = 1;
      } else if (this.$route.name.includes("bikes")) {
        this.view = true;
        this.vehiclesCurrent = 1;
      }
    },

    changeOrder() {
      if (this.orderCurrent < 1) {
        this.orderCurrent++;
      } else {
        this.orderCurrent = 0;
      }
      this.settingsActive = false;
      this.agentsActive = false;
      this.view = false;
      this.show = !this.show;
      this.vehiclesCurrent = 0;
    },

    startHover() {
      this.orderCurrent = 1;
      this.show = true;
    },

    stopHover() {
      if (this.$route.name.includes("active")) {
        this.orderCurrent = 1;
        this.show = true;
        this.view = false;
      } else if (this.$route.name.includes("cancelled")) {
        this.orderCurrent = 1;
        this.show = true;
        this.view = false;
      } else if (this.$route.name.includes("delivered")) {
        this.orderCurrent = 1;
        this.show = true;
        this.view = false;
      } else if (this.$route.name.includes("pending")) {
        this.orderCurrent = 1;
        this.show = true;
        this.view = false;
      } else {
        this.show = false;
        this.orderCurrent = 0;
      }
    },

    startHoverVehicles() {
      this.vehiclesCurrent = 1;
      this.view = true;
    },

    stopHoverVehicles() {
      if (this.$route.name.includes("bikes")) {
        this.vehiclesCurrent = 1;
        this.view = true;
        this.show = false;
      } else if (this.$route.name.includes("vans")) {
        this.vehiclesCurrent = 1;
        this.view = true;
        this.show = false;
      } else if (this.$route.name.includes("trucks")) {
        this.vehiclesCurrent = 1;
        this.view = true;
        this.show = false;
      } else {
        this.view = false;
        this.vehiclesCurrent = 0;
      }
    },

    changeVehicles() {
      if (this.vehiclesCurrent < 1) {
        this.vehiclesCurrent++;
      } else {
        this.vehiclesCurrent = 0;
      }
      this.settingsActive = false;
      this.agentsActive = false;
      this.show = false;
      this.view = !this.view;
      this.orderCurrent = 0;
    },
  },
};
</script>

<style scoped>
.topbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  background: #ffffff;
  height: 72px;
  display: flex;
  flex-direction: row;
  justify-content: end;
}

.bell {
  margin: auto 67px auto 0;
  width: 32px;
  height: 32px;
}

.name {
  margin: auto 8px auto 0;
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #575757;
}

.online {
  margin: auto 64px auto 0;
  width: 24px;
  height: 24px;
}

.sidebar {
  width: 320px;
  height: 100vh;
  background-color: #ffffff;
  top: 0;
  left: 0;
  display: flex;
  flex-direction: column;
  position: fixed;
  box-shadow: 0px 6px 18px 0px #0000000a;
}

.logo-container {
  display: flex;
  flex-direction: row;
  margin: 48px 0 48px 48px;
}

.logo {
  margin: 0 21px 0 0;
}

.xyz-text {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 20px;
  margin: 0 0 0 0;
}

.siderule {
  width: 100%;
  color: #f3f3f3;
  border: 1px solid #f3f3f3;
}

.siderule1 {
  width: 100%;
  color: #f3f3f3;
  border: 1px solid #f3f3f3;
  margin-top: 26px;
}

.navbar {
  display: flex;
  flex-direction: column;
}

.navitem1 {
  margin: 32px 0 0 24px;
  display: flex;
  align-items: center;
  flex-direction: row;
  background: #ffffff;
  width: 272px;
  height: 64px;
  text-decoration: none;
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 500;
  font-size: 16px;
  line-height: 24px;
  color: #666666;
  transition: 0.3s cubic-bezier(1, 0.39, 1, 2.52);
}

.navitem2 {
  margin: 0 0 0 24px;
  display: flex;
  flex-direction: row;
  background: #ffffff;
  width: 272px;
  height: 64px;
  text-decoration: none;
  cursor: pointer;
  transition: 0.3s cubic-bezier(1, 0.39, 1, 2.52) 5s;
}

.navitem3 {
  margin: 0 0 0 24px;
  display: flex;
  flex-direction: row;
  align-items: center;
  background: #ffffff;
  width: 272px;
  height: 64px;
  text-decoration: none;
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #666666;
  transition: 0.3s cubic-bezier(1, 0.39, 1, 2.52);
}

.navitem4 {
  margin: 0 0 0 24px;
  display: flex;
  flex-direction: row;
  background: #ffffff;
  width: 272px;
  height: 64px;
  text-decoration: none;
  cursor: pointer;
  transition: 0.3s cubic-bezier(1, 0.39, 1, 2.52);
}

.navitem5 {
  margin: 24px 0 0 24px;
  display: flex;
  flex-direction: row;
  align-items: center;
  background: #ffffff;
  width: 272px;
  height: 64px;
  text-decoration: none;
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #666666;
  transition: 0.3s cubic-bezier(1, 0.39, 1, 2.52);
}

a.nuxt-link-exact-active {
  background: #fbfbfb;
  border-left: 6px solid #d9b608;
  font-size: 18px;
  font-weight: 500;
  color: #000000;
  font-family: "DM Sans";
  font-style: normal;
}

.dashboardimg {
  width: 25px;
  height: 21.49px;
  margin: auto 21px auto 29px;
}

.dashboardtext {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 500;
  font-size: 16px;
  line-height: 24px;
  color: #666666;
  margin: auto auto auto 21px;
  text-decoration: none;
}

.ordersimg {
  width: 25px;
  height: 23.04px;
  margin: auto 0 auto 27px;
}

.orderstext {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #666666;
  margin: auto auto auto 21px;
  text-decoration: none;
}

.agentsimg {
  width: 25px;
  height: 25.6px;
  margin: auto 21px auto 29px;
}

.vehiclestext {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #666666;
  margin: auto auto auto 21px;
  text-decoration: none;
}

.vehiclesimg {
  width: 25px;
  height: 20.8px;
  margin: auto 0 auto 29px;
}

.settingsimg {
  width: 25px;
  height: 25.6px;
  margin: auto 21px auto 29px;
}

.orderDD {
  display: flex;
  flex-direction: row;
}

.verticalrule {
  width: 2px;
  height: 220px;
  background: #c8c8c8;
  margin-left: 65px;
  position: absolute;
}

.verticalrule1 {
  width: 2px;
  height: 169px;
  background: #c8c8c8;
  margin-left: 65px;
  position: absolute;
}

.orderview {
  display: flex;
  flex-direction: column;
}

.orderitems1 {
  margin: 0 auto 0 63px;
  text-decoration: none;
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 56px;
  color: #666666;
  width: 215px;
  height: 56px;
  transition: 0.3s cubic-bezier(1, 0.39, 1, 2.52);
}

.orderitems2 {
  margin: 0 auto 0 63px;
  text-decoration: none;
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 56px;
  color: #666666;
  width: 215px;
  height: 56px;
  transition: 0.3s cubic-bezier(1, 0.39, 1, 2.52);
}

.orderitems3 {
  margin: 0 auto 0 63px;
  text-decoration: none;
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 56px;
  color: #666666;
  width: 215px;
  height: 56px;
  transition: 0.3s cubic-bezier(1, 0.39, 1, 2.52);
}

.orderitems4 {
  margin: 0 auto 0 63px;
  text-decoration: none;
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 56px;
  color: #666666;
  width: 215px;
  height: 56px;
  transition: 0.3s cubic-bezier(1, 0.39, 1, 2.52);
}

.vehicleitem1 {
  margin: 0 auto 0 63px;
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 56px;
  color: #666666;
  background: #ffffff;
  width: 215px;
  height: 56px;
  text-decoration: none;
  transition: 0.3s cubic-bezier(1, 0.39, 1, 2.52);
}

.vehicleitem2 {
  margin: 0 auto 0 63px;
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 56px;
  color: #666666;
  background: #ffffff;
  width: 215px;
  height: 56px;
  text-decoration: none;
  transition: 0.3s cubic-bezier(1, 0.39, 1, 2.52);
}

.vehicleitem3 {
  margin: 0 auto 0 63px;
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 56px;
  color: #666666;
  background: #ffffff;
  width: 215px;
  height: 56px;
  text-decoration: none;
  transition: 0.3s cubic-bezier(1, 0.39, 1, 2.52);
}

.vtext {
  margin: auto 0 auto 32px;
}
</style>