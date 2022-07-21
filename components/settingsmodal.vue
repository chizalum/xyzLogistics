<template>
  <div class="modal-backdrop">
    <div class="main-modal">
      <input type="text" class="name" placeholder="Name">
      <input type="text" class="number" placeholder="Number">
      <input type="text" class="mail" placeholder="Email Address">
      <input type="text" class="role" placeholder="Role">
      <button class="button" @click="$emit('closeModal')">Add</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'settingsmodal',
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

.main-modal {
  position: fixed;
  margin: auto auto auto auto;
  height: 456px;
  width: 532px;
  background: #FFFEFA;
  display: flex;
  flex-direction: column;
}

.name{
  width: 364px;
  height: 48px;
  background: #F8F8F8;
  border-radius: 8px;
  margin: 64px auto 0 auto;
  border: none;
}

.name::placeholder{
  padding-left: 32px; 
}

.number{
  width: 364px;
  height: 48px;
  background: #F8F8F8;
  border-radius: 8px;
  margin: 24px auto 0 auto;
  border: none;
}

.number::placeholder{
  padding-left: 32px;
}

.mail{
  width: 364px;
  height: 48px;
  background: #F8F8F8;
  border-radius: 8px;
  margin: 24px auto 0 auto;
  border: none;
}

.mail::placeholder{
  padding-left: 32px; 
}

.role{
  width: 364px;
  height: 48px;
  background: #F8F8F8;
  border-radius: 8px;
  margin: 24px auto 0 auto;
  border: none;
}

.role::placeholder{
  padding-left: 32px; 
}

.button{
  width: 364px;
  height: 48px;
  background: #FFD60A;
  border-radius: 8px;
  border: none;  
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 24px;
  color: #000000;
  margin: 24px auto 0 auto;
}
</style>