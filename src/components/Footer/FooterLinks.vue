<template>
  <div class="wrap">
    <a 
      href="#" 
      class="links-list__title"
    >{{title}}</a>
    <a 
      class="links-list__link" 
      v-for="link in links" 
      :key="link.name"
    >{{link.name}}</a>
  </div>
</template>

<script>
export default {
  name:'',
  props: {
    title: String,
    links: Array
  },
  data: () => ({
  })
}
</script>

<style scoped>
.wrap {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.links-list__title {
  color: #fff;
  text-decoration: none;
  font-weight: bold;
  text-transform: uppercase;
  padding-bottom: 20px;
  font-size: 14px;
}

.links-list__title:hover {
  color: #cccccc;
}

.links-list__link {
  color: #999;
  font-size: 12px;
  padding-bottom: 15px;
  cursor: pointer;
}

.links-list__link:hover {
  color: #fff;
}

</style>