<template>
  <div class="allscreen">
    <h1 class="vehicles">Vehicles</h1>
    <h2 class="manage">
      Manage all your dispatchers, assign orders, and track orders here.
    </h2>
    <nav class="navbar">
      <router-link to="/vans" class="navlink1">Vans</router-link>
      <router-link to="/trucks" class="navlink2">Trucks</router-link>
      <router-link to="/bikes" class="navlink3">Bikes</router-link>
    </nav>
    <hr class="horizontalrule" />
    <div class="infobar">
      <div>
        <input type="search" placeholder="Search" class="searchbar" />
      </div>
      <div class="moreinfo">
        <div class="infogroups">
          <p class="infotext">
            Vehicle
          </p>
          <img src="droparrow.png" class="droparrow" alt="droparrow" />
        </div>
        <div class="infogroups">
          <p class="infotext">Condition</p>
          <img src="droparrow.png" class="droparrow" alt="droparrow" />
        </div>
        <div class="infogroups">
          <p class="infotext">Status</p>
          <img src="droparrow.png" class="droparrow" alt="droparrow" />
        </div>
        <div class="infogroups">
          <p class="infotext">Date</p>
          <img src="droparrow.png" class="droparrow" alt="droparrow" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Orderhead",
};
</script>

<style scoped>
.allscreen {
  height: auto;
  width: auto;
  white-space: nowrap;
  background: #fffefa;
}

.vehicles {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 700;
  font-size: 25px;
  line-height: 40px;
  color: #000000;
  margin: 96px 0 0 368px;
}

.manage {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #575757;
  margin: 8px 0 0 368px;
}

.navbar {
  display: flex;
  flex-direction: row;
  margin: 32px 0 0 368px;
  white-space: nowrap;
}

.navlink1 {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  min-width: auto;
  min-height: 52px;
  line-height: 24px;
  color: #777777;
  margin: 0 32px 0 0;
  text-decoration: none;
  transition: 0.3s cubic-bezier(1, 0.39, 1, 2.52);
}

.navlink2 {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  min-width: auto;
  min-height: 52px;
  line-height: 24px;
  color: #777777;
  margin: 0 32px 0 0;
  text-decoration: none;
  transition: 0.3s cubic-bezier(1, 0.39, 1, 2.52);
}

.navlink3 {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  min-width: auto;
  min-height: 52px;
  line-height: 24px;
  color: #777777;
  margin: 0 32px 0 0;
  text-decoration: none;
  transition: 0.3s cubic-bezier(1, 0.39, 1, 2.52);
}

a.nuxt-link-exact-active {
  font-weight: 700;
  color: #000000;
  border-bottom: 4px solid #d9b608;
  font-size: 18px;
}

.horizontalrule {
  width: 1120px;
  height: 0px;
  border: 1px solid #f3f3f3;
  margin: 0 0 0 320px;
}

.infobar {
  display: flex;
  flex-direction: row;
  margin: 32px 0 0 368px;
  height: 40px;
}

.searchbar {
  width: 590px;
  height: 40px;
  left: 368px;
  top: 272px;
  border: 1px solid #e4e4e4;
  border-radius: 8px;
  margin: 0 27px 0 0;
  padding-left: 32px;
}

.moreinfo {
  display: flex;
  flex-direction: row;
  width: 452px;
  height: 40px;
  border: 1px solid #e4e4e4;
  border-radius: 8px;
  white-space: nowrap;
  padding: 0;
}

.infogroups {
  display: flex;
  flex-direction: row;
  margin: 0 36px 0 0;
}

.infogroups:nth-child(1) {
  margin-left: 32px;
}

.infotext {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 21px;
  color: #000000;
  margin: auto 12px auto 0;
}

.droparrow {
  height: 4px;
  width: 8px;
  margin: auto 0 auto 0;
}

</style>
