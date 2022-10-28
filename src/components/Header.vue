<template>
  <div class="header">
      <div class="wrap">
        <img class="logo" src="@/assets/TVOE-logo.svg" alt="TVOE">
        <SelectCity/>
      </div>
      <HeaderNavigation/>
  </div>
</template>

<script>
import HeaderNavigation from './HeaderNavigation'
import SelectCity from './SelectCity'
export default {
  name: 'Header',
  components: {
    HeaderNavigation,
    SelectCity
  }
}
</script>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  padding: 20px;
  padding-bottom: 17px;
}
.wrap {
  display: flex;
}
.logo {
  max-width: 129px;
  max-height: 45px;
  margin-right: 107px;
  margin-left: 10px;
}

</style>