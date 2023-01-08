<template>
  <button class="delivery-modal" @click="reloadPage" v-if="isRouterAlive">
    <span class="delivery-modal__text">Бесплатная доставка от 2 000 руб. Самовывоз из магазинов - бесплатно</span>
    <img 
    class="delivery-modal__img" 
    @click="closeModal"
    src="https://img.icons8.com/material-rounded/24/FFFFFF/delete-sign.png" 
    alt="Close"/>
  </button>
</template>

<script>
export default {
  name: 'MDelivery',
  // inject: ['reload'],
  // provide: () => ({
  //   reload: this.reloadPage
  // }),
  data: () => ({
    isRouterAlive: true,
  }),
  methods: {
    reloadPage(){
      this.isRouterAlive = false
      this.$nextTick(function() {
        this.isRouterAlive = true
        this.message({
          message: 'hello',
          type: 'success'
        })
      })
    },
    closeModal() {
      this.$emit('closeModal')
    }
  }
}
</script>

<style scoped>
.delivery-modal {
  width: 100%;
  max-height: 50px;
  background-color: #000;
  color: #fff;
  padding: 11px;
  cursor: pointer;
}

.delivery-modal__text {
  font-size: 14px;
}

/* button {
  
  background-color: #000;

} */

img {
  max-width: 12px;
  position: absolute;
  right: 130px;
  top: 15px;
}
</style>