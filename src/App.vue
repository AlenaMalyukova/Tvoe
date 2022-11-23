<template>
  <div id="app">
    <MDelivery 
      v-if="isModalVisible"
      @closeModal="closeModal"/>
    <Header></Header>
    <Menu></Menu>
    
    <MainBanner></MainBanner>
    <BestOffer/>
    <Categories/>
    <AboutCompany/>
  </div>
</template>

<script>
import Header from './components/Header'
import Menu from './components/Menu'
import MainBanner from './components/MainBanner' 
import BestOffer from './components/BestOffer'
import MDelivery from './components/modals/MDelivery'
import Categories from './components/Categories'
import AboutCompany from './components/AboutCompany'

export default {
  name: 'App',
  components: {
    Header,
    Menu,
    MainBanner,
    BestOffer,
    MDelivery,
    Categories,
    AboutCompany
},
  data: () => ({
    isModalVisible: true
  }),
  methods: {
    closeModal() {
      this.isModalVisible = false
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
body {
  margin: 0 auto;
}
</style>
