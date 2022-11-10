<template>
  <div class="cards-wrap">
    <div 
      class="card" 
      v-for="card in hitList" 
      :key="card.art" 
      @mouseover="mouseOver(card.art)" 
      @mouseleave="mouseLeave">
        <div class="card__icon">{{ card.category }}</div>
        <img class="card__img" :src="card.img" alt="img">
        <div class="info">
          <div class="info__price">{{ card.price }}</div>
          <div class="info__art">{{ card.art }}</div>
          <a class="info__desc" href=card.link>{{ card.desc }}</a> 
        </div>
        <DropDownCard v-if="isDropDown && card.art === selectedCard"/>
    </div>
  </div>
</template>

<script>
import DropDownCard from './DropDownCard'
export default {
  name:'BestOfferHit',
  components: {
    DropDownCard
  },
  data: () => ({
    isDropDown: false,
    selectedCard: null,
    hitList: [
      {
        category: 'hit',
        img: 'https://tvoe.ru/img/2tuadr2/product/900/1200/8/4620123523680-1.jpg',
        art: 'Арт.: 94768',
        price: '3 999 руб.',
        desc: 'Толстовка с капюшоном на молнии ВПШ 4.0 CHANGES',
        link: 'https://tvoe.ru/product/khudi-vpsh-3-0-chernyy-94768/#1016504'
      },
      {
        category: 'hit',
        img: 'https://tvoe.ru/img/1e0chvh/product/410/547/8/4670080053683-2.jpg',
        art: 'Арт.: 73771',
        price: '799 руб.',
        desc: 'Базовая плотная футболка',
        link: 'https://tvoe.ru/product/futbolka-belyy-73771/#529184'
      },
      {
        category: 'hit',
        img: 'https://tvoe.ru/img/1i0h1ji/product/410/547/8/4620123190660-2.jpg',
        art: 'Арт.: A6624',
        price: '5 999 руб.',
        desc: 'Пуховик с капюшоном',
        link: 'https://tvoe.ru/product/kurtka-na-sintepone-zelenyy-a6624/#1008068'
      },
      {
        category: 'hit',
        img: 'https://tvoe.ru/img/3eq4q51/product/410/547/8/4670080055342-2.jpg',
        art: 'Арт.: 73783',
        price: '884 руб.',
        desc: 'Тонкие спортивные брюки',
        link: 'https://tvoe.ru/product/sportivnye-shtany-dlya-fitnesa-chernyy-73783/#351775'
      },
      {
        category: 'hit',
        img: 'https://tvoe.ru/img/3q91b26/product/410/547/8/4660053804374-2.jpg',
        art: 'Арт.: A6560',
        price: '4 999 руб.',
        desc: 'Дутая оверсайз куртка с капюшоном',
        link: 'https://tvoe.ru/product/kurtka-zefirka-chernyy-a6560/#981011'
      }
    ],
  }),
  methods: {
    mouseOver(art) {
      this.isDropDown = true
      this.selectedCard = art
    },
    mouseLeave() {
      this.isDropDown = false
      this.selectedCard = null
    }
  }
}
</script>

<style scoped>
.cards-wrap {
  margin: 30px;
  display: flex;
  flex-wrap: wrap;
  background-color: #fff;
}

.card {
  max-width: 205px;
  max-height: 407px;
  padding: 25px;
  position: relative;
  border: 1px solid #ececec;
  box-sizing: content-box;
}

.card:hover {
  box-shadow: 0 0 10px 5px #ececec;
}

.card__icon {
  background-color: #2992d9;
  color: #fff;
  border-radius: 2px;
  position: absolute;
  top: 25px;
  left: 25px;
  width: 30px;
  height: 20px;
  padding: 2px;
  text-transform: uppercase;
  font-size: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.card__img {
  width: 100%;
}

.info {
  max-height: 130px;
  height: 100%;
  display: flex;
  flex-direction: column;
  text-align: left;
  font-size: 13px;
}

.info__price {
  padding-top: 20px;
  font-size: 16px;
  padding-bottom: 10px;
  color: #000;
  font-weight: bold;
}

.info__art {
  color: gray;
  font-size: 12px;
  padding-bottom: 5px;
}

.info__desc {
  font-size: 14px;
  line-height: 1.8;
  padding-bottom: 30px;
  cursor: pointer;
  color: #000;
  text-decoration: none;
  overflow: hidden;
  -webkit-line-clamp: 2;
  display: -webkit-box;
  -webkit-box-orient: vertical;
}
</style>