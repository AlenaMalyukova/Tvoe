<template>
    <div class="cards-wrap">
      <div class="card" v-for="card in hitList" :key="card.art">
        <div class="card__icon">{{ card.category }}</div>
        <img class="card__img" :src="card.img" alt="img">
        <div class="info">
          <div class="info__price">{{ card.price }}</div>
          <div class="info__art">{{ card.art }}</div>
          <a class="info__desc" href="">{{ card.desc }}</a>
        </div>
      </div>
    </div>
</template>

<script>
export default {
  name: 'BestOfferNew',
  data: () => ({
    hitList: [
      {
        category: 'new',
        img: 'https://tvoe.ru/img/385or3v/product/410/547/8/4620123523123-2.jpg',
        art: 'Арт.: 94359',
        price: '1 299 руб.',
        desc: 'Футболка Музей русского импрессионизма Евгений Столица «Статуя Гермеса в парке»',
      },
      {
        category: 'new',
        img: 'https://tvoe.ru/img/13k5o7q/product/410/547/8/4620123531005-00.jpg',
        art: 'Арт.: 94354',
        price: '2 799 руб.',
        desc: 'Свитшот Музей русского импрессионизма Тит Дворников «У моря»',
      },
      {
        category: 'new',
        img: 'https://tvoe.ru/img/11aflmf/product/410/547/8/4620123494744.jpg',
        art: 'Арт.: 93832',
        price: '707 руб.',
        desc: 'Термолонгслив',
      },
      {
        category: 'new',
        img: 'https://tvoe.ru/img/35pmtv8/product/410/547/8/4620123426370.jpg',
        art: 'Арт.: A9955',
        price: '2 499 руб.',
        desc: 'Махровый домашний комплект с надписью Programmer',
      },
      {
        category: 'new',
        img: 'https://tvoe.ru/img/reqt9/product/410/547/8/4620123358794.jpg',
        art: 'Арт.: A9918',
        price: '2 999 руб.',
        desc: 'Махровый домашний комплект с принтом',
      }
    ]
  }),
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
  /* max-height: 300px; */
  padding: 25px;
  position: relative;
  border: 1px solid #ececec;
  box-sizing: content-box;
}

.card__icon {
  background-color: #636363;
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
  padding-bottom: 5px;
  color:#000;
  font-weight: bold;
}

.info__art {
  color: gray;
  font-size: 12px;
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