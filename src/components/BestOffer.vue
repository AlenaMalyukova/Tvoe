<template>
  <div class="wrap-cards">
    <div class="best-offer">
      <div class="best-offer__title">Лучшие предложения</div>
      <div class="filter">
        <button
          v-for="item in categories"
          :key="item"
          :class="{active: currentCategory === item}"
          @click="filter(item)">
          {{item}}
        </button>
      </div>
    </div>
    <div class="cards">
      <Cards :list='currentList'/>
    </div>
  </div>
</template>

<script>
import Cards from './Cards'

export default {
  name: 'BestOffer',
  components: {
    Cards,
  },
  props: {
    title: String
  },
  data: () => ({
    currentCategory: 'hit',
    categories: [
      'hit',
      'new',
      'sale'
    ],
    listHit: [
      {
        category: 'hit',
        img: 'https://tvoe.ru/img/2tuadr2/product/900/1200/8/4620123523680-1.jpg',
        art: 'Арт.: 94768',
        price: 3999,
        desc: 'Толстовка с капюшоном на молнии ВПШ 4.0 CHANGES',
        link: 'https://tvoe.ru/product/khudi-vpsh-3-0-chernyy-94768/#1016504'
      },
      {
        category: 'hit',
        img: 'https://tvoe.ru/img/1e0chvh/product/410/547/8/4670080053683-2.jpg',
        art: 'Арт.: 73771',
        price: 799,
        desc: 'Базовая плотная футболка',
        link: 'https://tvoe.ru/product/futbolka-belyy-73771/#529184'
      },
      {
        category: 'hit',
        img: 'https://tvoe.ru/img/1i0h1ji/product/410/547/8/4620123190660-2.jpg',
        art: 'Арт.: A6624',
        price: 5999,
        desc: 'Пуховик с капюшоном',
        link: 'https://tvoe.ru/product/kurtka-na-sintepone-zelenyy-a6624/#1008068'
      },
      {
        category: 'hit',
        img: 'https://tvoe.ru/img/3eq4q51/product/410/547/8/4670080055342-2.jpg',
        art: 'Арт.: 73783',
        price: 884,
        desc: 'Тонкие спортивные брюки',
        link: 'https://tvoe.ru/product/sportivnye-shtany-dlya-fitnesa-chernyy-73783/#351775'
      },
      {
        category: 'hit',
        img: 'https://tvoe.ru/img/3q91b26/product/410/547/8/4660053804374-2.jpg',
        art: 'Арт.: A6560',
        price: 4999,
        desc: 'Дутая оверсайз куртка с капюшоном',
        link: 'https://tvoe.ru/product/kurtka-zefirka-chernyy-a6560/#981011'
      }
    ],
    listNew: [
      {
        category: 'new',
        img: 'https://tvoe.ru/img/385or3v/product/410/547/8/4620123523123-2.jpg',
        art: 'Арт.: 94359',
        price: 1299,
        desc: 'Футболка Музей русского импрессионизма Евгений Столица «Статуя Гермеса в парке»',
        link: 'https://tvoe.ru/product/futbolka-muzey-russkogo-impressionizma-korichnevyy-94359/#1022717'
      },
      {
        category: 'new',
        img: 'https://tvoe.ru/img/13k5o7q/product/410/547/8/4620123531005-00.jpg',
        art: 'Арт.: 94354',
        price: 2799,
        desc: 'Свитшот Музей русского импрессионизма Тит Дворников «У моря»',
        link: 'https://tvoe.ru/product/svitshot-muzey-russkogo-impressionizma-svetlo-goluboy-94354/#1022691'
      },
      {
        category: 'new',
        img: 'https://tvoe.ru/img/11aflmf/product/410/547/8/4620123494744.jpg',
        art: 'Арт.: 93832',
        price: 707,
        desc: 'Термолонгслив',
        link: 'https://tvoe.ru/product/termolongsliv-chernyy-93832/'
      },
      {
        category: 'new',
        img: 'https://tvoe.ru/img/35pmtv8/product/410/547/8/4620123426370.jpg',
        art: 'Арт.: A9955',
        price: 2499,
        desc: 'Махровый домашний комплект с надписью Programmer',
        link: 'https://tvoe.ru/product/makhrovyy-domashniy-komplekt-s-nadpisyu-programmer-chernyy-a9955/'
      },
      {
        category: 'new',
        img: 'https://tvoe.ru/img/reqt9/product/410/547/8/4620123358794.jpg',
        art: 'Арт.: A9918',
        price: 2999,
        desc: 'Махровый домашний комплект с принтом',
        link: 'https://tvoe.ru/product/makhrovyy-domashniy-komplekt-s-printom-seryy-a9918/'
      }
    ],
    listSale: [
      {
        category: 'sale',
        img: 'https://tvoe.ru/img/2qnin6i/product/410/547/8/4620123498292-5.jpg',
        art: 'Арт.: 94771',
        price: 1999,
        oldPrice: 2499,
        desc: 'Спортивные брюки Color Basic',
        link: 'https://tvoe.ru/product/sportivnye-bryuki-color-basics-svetlo-seryy-melanzh-94771/#1016750'
      },
      {
        category: 'sale',
        img: 'https://tvoe.ru/img/fbcgo8/product/410/547/8/4620123497875-6.jpg',
        art: 'Арт.: 94772',
        price: 1799,
        oldPrice:3299,
        desc: 'Утепленное худи оверсайз Color Basic',
        link: 'https://tvoe.ru/product/khudi-color-basics-svetlo-seryy-melanzh-94772/#1016774'
      },
      {
        category: 'sale',
        img: 'https://tvoe.ru/img/3kne94o/product/410/547/8/4620123197782.jpg',
        art: 'Арт.: А6625',
        price: 3999,
        oldPrice: 5999,
        desc: 'Куртка на синтепоне',
        link: 'https://tvoe.ru/product/kurtka-na-sintepone-temno-bezhevyy-a6625/#1009455'
      },
      {
        category: 'sale',
        img: 'https://tvoe.ru/img/fjo74v/product/410/547/8/4620123517931-01.jpg',
        art: 'Арт.: A94412',
        price: 2672,
        oldPrice: 3299,
        desc: 'Худи с принтом Наруто',
        link: 'https://tvoe.ru/product/khudi-s-printom-naruto-chernyy-94412/#1016250'
      },
      {
        category: 'sale',
        img: 'https://tvoe.ru/img/23sruhk/product/410/547/8/4660053803070.jpg',
        art: 'Арт.: A6553',
        price: 2949,
        oldPrice: 4999,
        desc: 'Куртка-зефирка',
        link: 'https://tvoe.ru/product/kurtka-zefirka-krasnyy-a6553/#1015577'
      }
    ],
    isVisibleBlock: false
  }),
  methods: {
    filter(category) {
    this.currentCategory = category
    }
  },
  computed: {
    currentList() {
      if (this.currentCategory === 'hit') {
        return this.listHit
      }

      if (this.currentCategory === 'new') {
        return this.listNew
      }

      return this.listSale
    },
  }
}
</script>

<style scoped>
.wrap-cards {
  display: flex;
  flex-direction: column;
  background-color: #f9f9fa;
  padding-bottom: 30px;
}
.best-offer {
  padding: 60px 30px 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.best-offer__title {
  font-size: 23px;
  font-weight: bold;
  color: #383838;
}

button {
  margin: 0 15px;
  border: none;
  text-transform: uppercase;
  background-color: inherit;
  cursor: pointer;
  font-size: 12px;
  padding: 0 0 4px ;
}

.active {
  border-bottom: 2px solid black;
}
</style>
