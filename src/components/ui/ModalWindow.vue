<template>
  <div class="wrap">
    <div class="background" @click="closeWin"></div>
    <div class="win">
      <button @click="closeWin" class="wrap-win__close">
        <img 
          src="https://img.icons8.com/material-rounded/24/737373/delete-sign.png" alt="Close">
      </button>
      <slot name="content"></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ModalWindow',
  methods: {
    closeWin() {
      this.$emit('closeWin')
    }
  }
}
</script>
<style scoped>
.background {
  position: fixed;
  background-color: black;
  opacity: .8;
  width: 100%;
  height: 100%;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1;
}

.win {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  padding: 35px 60px 70px;
  background: #fff;
  max-width: 380px;
  height: auto;
  width: 100%;
  border-radius: 3px;
  z-index: 2;
}

.wrap-win__close {
  border: none;
  background-color: #fff;
  cursor: pointer;
  position: absolute;
  top: 10px;
  right: 9px;
}

</style>