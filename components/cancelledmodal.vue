<template>
  <div class="modal-backdrop" @click="$emit('closeModal')">
    <div class="image-container" @click="$emit('closeModal')">
        <img :src="img" class="image">
    </div>
  </div>
</template>

<script>
export default {
  name: 'cancelledmodal',

  data() {
    return{
        img: 'modalimage.png',
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

.image-container {
  position: fixed;
  margin: auto auto auto auto;
  height: 313px;
  width: 439px; 
  border-radius: 8px;
}

.image {
  margin: auto auto auto auto;
}
</style>