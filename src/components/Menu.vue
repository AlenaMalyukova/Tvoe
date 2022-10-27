<template>
  <div class="menu-wrap">

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
        link: '/woman'
      },
      {
        name: 'Верхняя одежда',
        link: '/woman'
      },
      {
        name: 'Специальные коллекции',
        link: '/woman'
      },
      {
        name: 'Новинки',
        link: '/woman'
      },
      {
        name: 'Распродажа',
        link: '/woman'
      }
    ]
  })
}
</script>

<style scoped>
.menu-wrap {
  display: flex;
  justify-content: space-between;
}
</style>