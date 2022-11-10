<template>
  <div class="wrap">
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
      <BestOfferHit v-if="currentCategory === 'hit'"/>
      <BestOfferNew v-if="currentCategory === 'new'"/>
      <BestOfferSale v-if="currentCategory === 'sale'"/>
    </div>
  </div>
</template>

<script>
import BestOfferHit from './BestOfferHit';
import BestOfferNew from './BestOfferNew';
import BestOfferSale from './BestOfferSale';

export default {
  name: 'BestOffer',
  components: {
    BestOfferHit,
    BestOfferNew,
    BestOfferSale
  },
  data: () => ({
    currentCategory: 'hit',
    categories: [
      'hit',
      'new',
      'sale'
    ],
    isVisibleBlock: false
  }),
  methods: {
    filter(category) {
    this.currentCategory = category
    }
  }
}
</script>

<style scoped>
.wrap {
  display: flex;
  flex-direction: column;
  background-color: #f9f9fa;
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

/* .cards {
  max-height: 450px;
} */
</style>
