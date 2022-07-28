<template>
  <div class="fullwidth">
    <nav class="navbar">
      <router-link to="/settings" class="navlink1">Users & Roles</router-link>
      <router-link to="/settings" class="navlink2">Account settings</router-link>
    </nav>
    <hr class="horizontalrule">
    <div class="searchbutton">
    <input type="search" class="searchbar" placeholder="Search">
    <button class="button" @click="openModal()">Add New</button>
    </div>
    <div class="title">
      <p class="name">Name</p>
      <p class="role">Role</p>
      <p class="number">Number</p>
      <p class="mail">Email Address</p>
      <p class="date">Date Added</p>
    </div>
    <div class="data">
      <p class="named">Jide ayomide</p>
      <p class="roled">Admin</p>
      <p class="numbered">08035368293</p>
      <p class="mailed">jidesamuel267@gmail.com</p>
      <p class="dated">12/6/22</p>
      <img src="dots.png" alt="options" class="dots">
    </div>
    <div class="data1">
      <p class="named">Jide ayomide</p>
      <p class="roled">Admin</p>
      <p class="numbered">08035368293</p>
      <p class="mailed">jidesamuel267@gmail.com</p>
      <p class="dated">12/6/22</p>
      <img src="dots.png" alt="options" class="dots">
    </div>
    <div class="data1">
      <p class="named">Jide ayomide</p>
      <p class="roled">Admin</p>
      <p class="numbered">08035368293</p>
      <p class="mailed">jidesamuel267@gmail.com</p>
      <p class="dated">12/6/22</p>
      <img src="dots.png" alt="options" class="dots">
    </div>
    <div class="data1">
      <p class="named">Jide ayomide</p>
      <p class="roled">Admin</p>
      <p class="numbered">08035368293</p>
      <p class="mailed">jidesamuel267@gmail.com</p>
      <p class="dated">12/6/22</p>
      <img src="dots.png" alt="options" class="dots">
    </div>
    <div class="data1">
      <p class="named">Jide ayomide</p>
      <p class="roled">Admin</p>
      <p class="numbered">08035368293</p>
      <p class="mailed">jidesamuel267@gmail.com</p>
      <p class="dated">12/6/22</p>
      <img src="dots.png" alt="options" class="dots">
    </div>
    <div class="data1">
      <p class="named">Jide ayomide</p>
      <p class="roled">Admin</p>
      <p class="numbered">08035368293</p>
      <p class="mailed">jidesamuel267@gmail.com</p>
      <p class="dated">12/6/22</p>
      <img src="dots.png" alt="options" class="dots">
    </div>
    <div class="data1">
      <p class="named">Jide ayomide</p>
      <p class="roled">Admin</p>
      <p class="numbered">08035368293</p>
      <p class="mailed">jidesamuel267@gmail.com</p>
      <p class="dated">12/6/22</p>
      <img src="dots.png" alt="options" class="dots">
    </div>
    <div class="data1">
      <p class="named">Jide ayomide</p>
      <p class="roled">Admin</p>
      <p class="numbered">08035368293</p>
      <p class="mailed">jidesamuel267@gmail.com</p>
      <p class="dated">12/6/22</p>
      <img src="dots.png" alt="options" class="dots">
    </div>
    <div class="data1">
      <p class="named">Jide ayomide</p>
      <p class="roled">Admin</p>
      <p class="numbered">08035368293</p>
      <p class="mailed">jidesamuel267@gmail.com</p>
      <p class="dated">12/6/22</p>
      <img src="dots.png" alt="options" class="dots">
    </div>
    <div class="data1">
      <p class="named">Jide ayomide</p>
      <p class="roled">Admin</p>
      <p class="numbered">08035368293</p>
      <p class="mailed">jidesamuel267@gmail.com</p>
      <p class="dated">12/6/22</p>
      <img src="dots.png" alt="options" class="dots">
    </div>
    <settingsmodal v-if="showModal" @closeModal="offModal" />
  </div>
</template>

<script>
export default {
    name: "settings",
    data() {
        return {
            showModal: false
        };
    },
    methods: {
        openModal() {
            this.showModal = true;
        },

        offModal() {
            this.showModal = false;
        }
    },
}
</script>

<style scoped>
.fullwidth{
height: 100vh;
width: 100vw;
}

.navbar{
display: flex;
flex-direction: row;
margin: 104px 0 0 368px;
white-space: nowrap;
}

.navlink1{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
min-width: auto;
min-height: 52px;
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
min-width: auto;
min-height: 52px;
line-height: 24px;
color: #777777;  
margin: 0 32px 0 0;
text-decoration: none;
}

a.nuxt-link-active{
font-weight: 700;
color: #000000;
border-bottom: 4px solid #D9B608;
}

.horizontalrule{
width: 1050px;
height: 0px;
left: 320px;
top: 144px;
background: #F3F3F3;
border: 1px solid #F3F3F3; 
margin: 0 0 0 320px;  
}

.searchbutton{
display: flex;
flex-direction: row;
}

.searchbar{
width: 711px;
height: 40px;
left: 368px;
top: 176px;
border: 1px solid #E4E4E4;
border-radius: 8px;   
margin: 32px 0 0 368px;
}

.button{
width: 184px;
height: 40px;
left: 1119px;
top: 176px;
background: #FFD60A;
border-radius: 8px;
border: none;  
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 14px;
line-height: 24px;
color: #000000;
margin: 32px 0 0 40px;
}

.title{
display: flex;
flex-direction: row;
margin: 32px 0 0 368px;
white-space: nowrap;
}

.name{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 0;
}

.role{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 148px;
}

.number{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 83px;
}

.mail{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 97px;
}

.date{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #CC5500;
margin: 0 0 0 150px;
}

.data{
width: 1207px;
height: 56px;
background: #FFFFFF; 
margin: 16px 0 0 344px;  
display: flex;
flex-direction: row;
white-space: nowrap;
}

.data1{
width: 1207px;
height: 56px;
background: #FFFFFF; 
margin: 8px 0 0 344px;  
display: flex;
flex-direction: row;
white-space: nowrap;   
}

.named{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #000000;
margin: auto 93px auto 24px;
}

.roled{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #000000;
margin: auto 69px auto 0;
}

.numbered{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #000000;
margin: auto 47px auto 0;
}

.mailed{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #000000;
margin: auto 56px auto 0;
}

.dated{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
color: #000000;
margin: auto 96px auto 0;
}

.dots{
height: 5.12px;
width: 25.60px;
margin: auto 0 auto 0;
}
</style>
