<template>
  <div class="cards-wrap">
    <div 
      class="card" 
      v-for="card in list" 
      :key="card.art" 
      @mouseover="mouseOver(card.art)" 
      @mouseleave="mouseLeave">
        <div 
          :class="`card__icon card__icon-${card.category}`">
          {{ card.category }}
        </div>
        <div class="card__icon-discount" v-if="card.category === 'sale'">
          {{`- ${discount(card.oldPrice, card.price)}%`}}
        </div>
        <img class="card__img" :src="card.img" alt="img">
        <div class="info">
          <div :class="`info-price info-price-${card.category}`">
            {{ `${card.price} руб.`}}
            <div class="info-price__old-price" v-if="card.category === 'sale'">{{ `${card.oldPrice} руб.` }}</div>
          </div>
          <div class="info__art">{{ card.art }}</div>
          <a class="info__desc" :href='card.link'>{{ card.desc }}</a> 
        </div>
        <DropDownCard v-if="isDropDown && card.art === selectedCard"/>
    </div>
  </div>
</template>

<script>
import DropDownCard from './DropDownCard'
export default {
  name:'Cards',
  components: {
    DropDownCard
  },
  props: {
    list: Array,
  },
  data: () => ({
    isDropDown: false,
    selectedCard: null,
  }),
  methods: {
    mouseOver(art) {
      this.isDropDown = true
      this.selectedCard = art
    },
    mouseLeave() {
      this.isDropDown = false
      this.selectedCard = null
    },
    discount(oldPrice, newPrice) {
      const difference = oldPrice - newPrice
      return Math.round(difference / oldPrice * 100)
    }
  }
}
</script>

<style scoped>
.cards-wrap {
  margin: 30px;
  display: flex;
  flex-wrap: wrap;
  /* width: 100%; */
}

.card {
  max-width: 205px;
  max-height: 397px;
  padding: 25px;
  position: relative;
  border: 1px solid #ececec;
  box-sizing: content-box;
  background-color: #fff;
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

.card__icon-new {
  background: #636363;
}

.card__icon-sale {
  background: #52cc00;
}

.card__icon-discount {
  height: 15px;
  width: auto;
  padding: 3px 10px;
  background-color: red;
  position: absolute;
  bottom: 147px;
  left: 25px;
  border-radius: 2px;
  font-size: 12px;
  font-weight: bold;
  color:#fff;
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

.info-price {
  padding-top: 20px;
  font-size: 16px;
  padding-bottom: 10px;
  color: #000;
  font-weight: bold;
  display: flex;
  align-items: center;
}

.info-price-sale {
  color: red;
}

.info-price__old-price {
  color: gray;
  text-decoration: line-through;
  padding-left: 15px;
  font-size: 13px;
  font-weight: normal;
}

.info__art {
  color: gray;
  font-size: 12px;
  padding-bottom: 5px;
}

.info__desc {
  font-size: 14px;
  line-height: 1.8;
  cursor: pointer;
  color: #000;
  text-decoration: none;
  overflow: hidden;
  -webkit-line-clamp: 2;
  display: -webkit-box;
  -webkit-box-orient: vertical;
}
</style>