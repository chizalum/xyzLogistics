<template>
  <div class="fullscreen">
    <form action="" class="form">
      <h1 class="welcome">Welcome back</h1>
      <p class="instructions">Enter your username and password</p>
      <input
        class="username"
        type="text"
        placeholder="username"
        required
        v-model="adminName"
      />
      <input
        class="password"
        type="text"
        placeholder="password"
        required
        v-model="adminPassword"
      />
      <button class="continuebtn" @click="changeRoute()">
        <router-link to="/loginpage" class="continue">Continue</router-link>
      </button>
    </form>
  </div>
</template>

<script>
export default {
  name: "loginpage",
  layout: "login",

  methods: {
    changeRoute() {
      this.$router.push("/dashboard");
    },
  },
};
</script>


<style scoped>
.fullscreen {
  height: 100vh;
  margin: 0 60% 0 0;
}

.form {
  display: flex;
  flex-direction: column;
  width: 50%;
  height: auto;
  margin: auto auto auto auto;
  position: absolute;
  top: 50%;
  -ms-transform: translateY(-50%);
  transform: translateY(-50%);
}

.welcome {
  width: 288px;
  height: 56px;
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 700;
  font-size: 40px;
  line-height: 56px;
  color: #000000;
  text-align: center;
  margin: 0 auto 0 auto;
}

.instructions {
  width: 261px;
  height: 24px;
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  text-align: center;
  color: #777777;
  margin: 8px auto 0 auto;
}

.username {
  box-sizing: border-box;
  width: 364px;
  max-width: 364px;
  height: 48px;
  background: #f8f8f8;
  border: 1px solid #f8f8f8;
  border-radius: 8px;
  margin: 40px auto 0 auto;
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 48px;
  color: #000000;
  padding-left: 32px;
}

.username:focus {
  border-color: #d9b608;
  outline: none;
}

.username::placeholder {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 21px;
  color: #7d7d7d;
}

.password {
  box-sizing: border-box;
  width: 364px;
  max-width: 364px;
  height: 48px;
  background: #f8f8f8;
  border: 1px solid #f8f8f8;
  border-radius: 8px;
  margin: 24px auto 0 auto;
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 48px;
  color: #000000;
  padding-left: 32px;
}

.password:focus {
  border-color: #d9b608;
  outline: none;
}

.password::placeholder {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 21px;
  color: #7d7d7d;
}

.continuebtn {
  width: 364px;
  height: 48px;
  background: #ffd60a;
  border-radius: 8px;
  border: none;
  margin: 40px auto 0 auto;
  cursor: pointer;
}

.continue {
  width: 63px;
  height: 24px;
  margin: auto;
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 24px;
  color: #000000;
  text-decoration: none;
}
</style>