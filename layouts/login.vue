<template>
  <div class="container">
    <div class="sign">
        <Signin />
    </div>
    <div class="next">
        <nuxt />
    </div>
   </div> 
</template>

<style>
body, html {
height: 100%;
margin: 0;
padding: 0;
}

.container{
height: 100vh;
width: 100vw;
padding: 0;
margin: 0;
}
.next{
width: 40%;
height: 100vh;
margin: 0 60% 0 0;
padding: 0;
}

.sign{
width: 60%;
height: 100vh;
margin: 0 0 0 40%;
position: fixed;
padding: 0;
}
</style>