<template>
  <div class="menu">
    <button class="menu-page" v-for="link in links" :key="link.name">{{link.name}}</button>
  </div>
</template>

<script>
export default {
  name: 'Menu',
  data: () => ({
    links: [
      {
        name: 'Женщины',
        link: '/woman'
      },
      {
        name: 'Мужчины',
        link: '/man'
      },
      {
        name: 'Верхняя одежда',
        link: '/outwear'
      },
      {
        name: 'Специальные коллекции',
        link: '/special-collection'
      },
      {
        name: 'Новинки',
        link: '/new'
      },
      {
        name: 'Распродажа',
        link: '/sale'
      }
    ]
  })
}
</script>

<style scoped>
.menu {
  display: flex;
  justify-content: space-between;
  border-top: 1px solid #ececec;
  border-bottom: 1px solid #ececec;
  padding: 0px 30px;
}

.menu-page {
  color: black;
  font-weight: bold;
  text-transform: uppercase;
  font-size: 13px;
  cursor: pointer;
  padding: 17px 55px;
  box-sizing: border-box;
  border:none;
  background-color: inherit;
  text-align: center;
  line-height: 1.5;
  /* letter-spacing: 1px; */
}

.menu-page:hover {
  background-color: #ececec;
}
</style>