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

<style scoped>
.container{
height: 100vh;
}
.next{
width: 40%;
height: 100vh;
margin: 0 60% 0 0;
}

.sign{
width: 60%;
height: 100vh;
margin: 0 0 0 40%;
}
</style>