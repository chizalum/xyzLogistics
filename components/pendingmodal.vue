<template>
  <div class="modal-backdrop">
    <div class="modal-container">
      <img src="close.png" class="close" @click="$emit('closeModal')">
      <p class="assign">Assign Rider</p>
      <div class="modal-flex">
        <p class="agent">Vehicle</p>
        <img src="gold-dropdown.png" class="droparrow1">
      </div>
      <div class="modal-flex">
        <p class="agent">Rider</p>
        <img src="gold-dropdown.png" class="droparrow">
      </div>
      <button class="assign-btn" @click="$emit('closeModal')"><span class="assign-text">Assign</span></button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'pendingmodal',

  data() {
    return{
    }
  }
}
</script>

<style scoped>
.modal-backdrop {
  height: 100vh;
  width: 100vw;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
}

.modal-container {
  position: fixed;
  margin: auto auto auto auto;
  width: 532px;
  height: 304px;
  background: #FFFEFA;
  text-align: center;
}

.close{
height: 16px;
width: 16px;
margin: 5px 0 0 512px;
}

.assign{
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 21px;
  color: #000000;
  margin: 11px auto 0 auto;  
}

.modal-flex{
  display: flex;
  flex-direction: row;
  width: 364px;
  height: 48px;
  justify-content: center;
  margin: 32px auto 0 auto;
  background: #F8F8F8;
  border-radius: 8px;
}

.agent{
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 21px;
  color: #7D7D7D;  
  margin: auto 0 auto 32px;
}

.droparrow {
  margin: auto 0 auto 264px;
}

.droparrow1 {
  margin: auto 0 auto 250px;
}

.assign-btn{
  width: 364px;
  height: 48px;
  background: #FFD60A;
  border-radius: 8px;
  border: none;
  margin: 24px auto 0 auto;
}

.assign-text{
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 24px;
  color: #000000; 
}
</style>