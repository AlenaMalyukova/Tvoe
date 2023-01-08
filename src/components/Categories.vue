<template>
  <div class="wrap-category">
    <div class="category" v-for="category in categoriesList" :key="category.title">
      <div class="text">
        <a class="text__title" :href="category.mainLink.link">
          {{category.mainLink.label}}
        </a>
        <div class="links">
          <a class="links__link" :href="category.linkWomen.link">
            {{category.linkWomen.label}}
          </a>
          <span>|</span>
          <a class="links__link" :href="category.linkMen.link">
            {{category.linkMen.label}}
          </a>
        </div>
      </div>
      <img :src="category.img" alt="">
    </div>
  </div>
</template>
<script>
export default {
  name: 'Categories',
  data: () => ({
    categoriesList: [
      {
        mainLink: {
          label: 'Водолазки',
          link: 'https://tvoe.ru/catalog/jenshchinam/odejda/vodolazki/'
        },
        linkWomen: {
          label: 'Для женщин',
          link: 'https://tvoe.ru/catalog/jenshchinam/odejda/vodolazki/'
        },
        linkMen: {
          label: 'Для мужчин',
          link: 'https://tvoe.ru/catalog/mujchinam/odejda/longslivy/'
        },
        img: 'https://tvoe.ru/upload/iblock/e0e/j15pdy4suk59e2befsnj2d9yaqakv0qv.jpg',
      },
      {
        mainLink: {
          label: 'Верхняя одежда',
          link: 'https://tvoe.ru/catalog/jenshchinam/verhnyaya-odezhda/'
        },
        linkWomen: {
          label: 'Для женщин',
          link: 'https://tvoe.ru/catalog/jenshchinam/verhnyaya-odezhda/'
        },
        linkMen: {
          label: 'Для мужчин',
          link: 'https://tvoe.ru/catalog/mujchinam/verhnyaya-odejda/'
        },
        img: 'https://tvoe.ru/upload/iblock/dfb/s712f2b16bo9r60x896nu2pntdeg19t2.jpg',
      },
      {
        mainLink: {
          label: 'Деним',
          link: 'https://tvoe.ru/catalog/jenshchinam/dlinsovaya-odezhda/'
        },
        linkWomen: {
          label: 'Для женщин',
          link: 'https://tvoe.ru/catalog/jenshchinam/dlinsovaya-odezhda/'
        },
        linkMen: {
          label: 'Для мужчин',
          link: 'https://tvoe.ru/catalog/mujchinam/dzhinsovaya-odezhda/'
        },
        img: 'https://tvoe.ru/upload/iblock/021/0abuuwmyg24a75wc0yi96r82yfansp2m.jpg',
      },
      {
        mainLink: {
          label: 'Толстовки',
          link: 'https://tvoe.ru/catalog/mujchinam/odejda/tolstovka/'
        },
        linkWomen: {
          label: 'Для женщин',
          link: 'https://tvoe.ru/catalog/jenshchinam/odejda/tolstovka/'
        },
        linkMen: {
          label: 'Для мужчин',
          link: 'https://tvoe.ru/catalog/mujchinam/odejda/tolstovka/'
        },
        img: 'https://tvoe.ru/upload/iblock/062/nn5hpcu5ws8ia1k7w1xluwmin5dz8srb.jpg',
      },
    ]
  })
}
</script>
<style scoped>
.wrap-category {
  padding: 65px 30px;
  background-color: #fff;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-gap: 30px;
}

.category {
  background-color: #f3f4f6;
  max-height: 400px;
  display: flex;
  padding-bottom: 15px;
  align-items: center;
  justify-content: flex-end;
  border-radius: 5px;
}

.text {
  text-align: justify;
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin: 0 auto;
}

a {
  text-decoration: none;
  color: #333;
}

.text__title {
  text-transform: uppercase;
  font-size: 23px;
  font-weight: bold;
  
}

.links {
  margin-top: 20px;
  font-size: 12px;
  letter-spacing: 1px;
}

img {
  max-height: 385px;
  border-radius: 0 5px 0 0;
  width: 50%;
}
</style>