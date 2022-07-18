<template>
 <div class="fullpage">
    <h1 class="welcome">Welcome back David</h1>
    <div class="stats">
      <div class="revenue">
        <p class="total">Total Revenue</p>
          <p class="amount">₦200k</p>
        <div class="facts">
          <p class="up">Up by 50k this month</p>
          <img src="greenarrow.png" alt="uparrow" class="greenarrow">
        </div>
      </div>
      <div class="active">
        <p class="order">Active Orders</p>
        <p class="twohundred">200</p>
        <div class="fact">
          <p class="down">Down by 50k this month</p>
        <img src="redarrow.png" alt="downarrow" class="redarrow">
        </div>
      </div>
      <div class="pending">
        <p class="pend">Pending Orders</p>
        <p class="fournine">49</p>
      </div>
      <div class="riders">
        <p class="ride">Active Riders</p>
        <p class="seveno">70</p>
      </div>
    </div>
    <hr class="horizontalrule">
    <div class="barchartdiv">
      <img src="barchart.png" class="barchart" alt="barchart">
    </div>
    <div class="vehiclesdiv">
      <img src="damagedvehicles.png" class="damagedvehicles" alt="">
      <img src="numbervehicles.png" class="numbervehicles" alt="">
    </div>
  </div>
</template>

<script>
export default {
    name: "dashboard",
}
</script>

<style scoped>
.fullpage{
  background: #FFFEFA;
  height: 100vh;
  width: 100vw;
}

.welcome{
   font-family: 'DM Sans';
   font-style: normal;
   font-weight: 400;
   font-size: 25px;
   line-height: 40px;
   color: #000000; 
   margin: 96px 0 0 344px;
}

.stats{
    display: flex;
    flex-direction: row;
    margin: 40px 0 0 368px;
    padding: 0;
    white-space: nowrap;
}

.revenue{
    width: 260px;
    height: 125px;
    left: 344px;
    top: 152px;
    border-right: 1px solid #F3F3F3;
    padding: 24px 0 0 24px;
    margin: 0;
    display: flex;
    flex-direction: column;
}

.active{
    width: 260px;
    height: 125px;
    left: 344px;
    top: 152px;
    border-right: 1px solid #F3F3F3;
    padding: 24px 0 0 24px;
    margin: 0;
    display: flex;
    flex-direction: column;
}

.pending{
    width: 260px;
    height: 125px;
    left: 344px;
    top: 152px;
    border-right: 1px solid #F3F3F3;
    padding: 24px 0 0 24px;
    margin: 0;
    display: flex;
    flex-direction: column;
}

.riders{
    width: 260px;
    height: 125px;
    left: 344px;
    top: 152px;
    border-right: 1px solid #F3F3F3;
    padding: 24px 0 0 24px;
    margin: 0;
    display: flex;
    flex-direction: column;
}

.total{
   font-family: 'DM Sans';
   font-style: normal;
   font-weight: 400;
   font-size: 14px;
   line-height: 21px;
   color: #000000;
   margin: 0 0 0 0;
}

.amount{
    font-family: 'DM Sans';
    font-style: normal;
    font-weight: 700;
    font-size: 40px;
    color: #000000;
    margin: 13px 0 0 0;
    line-height: 56px;
}

.facts{
    display: flex;
    flex-direction: row;
    margin: 15px 0 0 0;
    align-items: center;
    height: 18.24px;
}

.up{
    font-family: 'DM Sans';
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 21px;
    color: #ADADAD;
}

.greenarrow{
    width: 18.24px;
    height: 18.24px;
    margin: 0 0 0 10.88px;
}

.order{
    font-family: 'DM Sans';
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 21px;
    color: #000000;
    margin: 0 0 0 0;
}

.twohundred{
    font-family: 'DM Sans';
    font-style: normal;
    font-weight: 700;
    font-size: 40px;
    line-height: 56px;
    color: #000000;
    margin: 13px 0 0 0;
    padding: 0;
}

.fact{
    display: flex;
    flex-direction: row;
    margin: 15px 0 0 0;
    height: 18.24px;
}

.down{
    font-family: 'DM Sans';
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 21px;
    color: #ADADAD;
    margin: 0 0 0 0;
}

.redarrow{
    height: 18.24px;
    width: 18.24px;
    margin: 0 0 0 10.88px;
}

.pend{
    font-family: 'DM Sans';
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 21px;
    color: #000000;
    margin: 0 0 0 0;
}

.fournine{
    font-family: 'DM Sans';
    font-style: normal;
    font-weight: 700;   
    font-size: 40px;
    line-height: 56px;
    color: #000000;
    margin: 13px 0 0 0;
}

.ride{
    font-family: 'DM Sans';
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 21px;
    color: #000000;
    margin: 0 0 0 0;
}

.seveno{
    font-family: 'DM Sans';
    font-style: normal;
    font-weight: 700;
    font-size: 40px;
    line-height: 56px;
    color: #000000;
    margin: 13px 0 0 0;
}

.horizontalrule{
    margin: 30px 0 0 320px;
    width: 1044px;
    color: #F3F3F3;
    border: 1px solid #F3F3F3;
}

.barchartdiv{
    margin: 32px 0 0 344px;
    padding: 0;
    border: none;
    width: 984px;
    height: 379px;
    object-fit: cover;
}

.barchart{
    width: 100%;
    height: 100%;
    margin: 0 0 0 0;
    padding: 0;
    object-fit: cover;
}

.vehiclesdiv{
    width: 984px;
    margin: 32px 0 0 344px;
    display: flex;
    flex-direction: row;
    align-content: space-between;
}
</style>
