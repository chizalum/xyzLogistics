<template>
    <div class="fullscreen">
      <form action="" class="form">
        <h1 class="welcome">Hello Prudence,</h1>
        <p class="instructions">Set your username and  password</p>
        <input class="username" type="text" placeholder="username" required>
        <input class="password" type="text" placeholder="password" required>
        <input class="password" type="text" placeholder="Confirm Password" required>
        <button class="continuebtn">
          <p class="continue">Continue</p>
        </button>
      </form>
    </div>
</template>

<script>
  export default {
    layout: 'login',
  }
</script>

<style scoped>

.fullscreen{
width: 40%;
height: 100vh;
margin: 0 60% 0 0;
}

.form{
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

.welcome{
width: 288px;
height: 56px;
font-family: 'DM Sans';
font-style: normal;
font-weight: 700;
font-size: 40px;
line-height: 56px;
color: #000000;
text-align: center;
margin: 0 auto 0 auto;
}

.instructions{
width: 261px;
height: 24px;
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 16px;
line-height: 24px;
text-align: center;
color: #777777;
margin: 8px auto 0 auto;
}

.username{
box-sizing: border-box;
width: 364px;
height: 48px;
background: #F8F8F8;
border: 1px solid #F8F8F8;
border-radius: 8px;
margin: 40px auto 0 auto;
}

.username:focus{
border-color: #D9B608;
outline: none;
}

.username::placeholder{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 14px;
line-height: 21px;
color: #7D7D7D;
padding-left: 32px;
}

.password{
width: 364px;
height: 48px;
background: #F8F8F8;
border-radius: 8px;
border: 1px solid #F8F8F8;
margin: 24px auto 0 auto;
}

.password:focus{
border-color: #D9B608;
outline: none;
}

.password::placeholder{
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 14px;
line-height: 21px;
color: #7D7D7D;
padding-left: 32px;
}

.continuebtn{
width: 364px;
height: 48px;
background: #FFD60A;
border-radius: 8px;
border: none;
margin: 40px auto 0 auto;
}

.continue{
width: 63px;
height: 24px;
margin: auto;
font-family: 'DM Sans';
font-style: normal;
font-weight: 400;
font-size: 14px;
line-height: 24px;
color: #000000;
}
</style>