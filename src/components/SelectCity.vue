<template>
  <div class="city-wrap">
    <button @click="openModal" class="wrap-btn">
      <span>{{city}}</span>
      <img src="https://img.icons8.com/material-sharp/24/1A1A1A/sort-down.png">
    </button>
    <ModalWindow 
      v-if="isModalVisible"
      @closeWin="closeModal">
      <template v-slot:content>
        <MSelectCity @selectCity="selectCity"/>
      </template>
    </ModalWindow>
  </div>
</template>

<script>
import ModalWindow from './ui/ModalWindow';
import MSelectCity from './modals/MSelectCity';

export default {
  name: 'SelectCity',
  components: {
    ModalWindow,
    MSelectCity
  },
  data: () => ({
    isModalVisible: false,
    city: 'Выбрать город'
  }),
  methods: {
    openModal() {
      this.isModalVisible = true
    },
    closeModal() {
      this.isModalVisible = false
    },
    selectCity(city) {
      this.city = city
      this.closeModal()
    }
  }
}
</script>

<style scoped>
.wrap-btn {
  border:none;
  background-color: #fff;
  padding: 0;
  max-height: 40px;
  cursor: pointer;
}
img {
  width: 8px;
}
</style>