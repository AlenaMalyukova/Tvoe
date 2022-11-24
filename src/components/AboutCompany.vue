<template>
  <div class="wrapper">
    <a href="#">О компании</a>
    <div class="wrap">
      <div class="text">
        <div class="text__title">
          ТВОЕ - интернет-магазин одежды, обуви и аксессуаров
        </div>
        <div class="text__desc">
          ТВОЕ – российский бренд одежды, обуви и аксессуаров. Собственные производственные площадки компании расположены в России, Белоруссии и Молдавии, розничная сеть насчитывает более 300 магазинов в четырех странах СНГ. Бренд занимает лидирующие позиции в сегменте online-продаж одежды.
        </div>
        <div class="text__desc">
          ТВОЕ регулярно выпускает коллекции в сотрудничестве с Disney, MARVEL, Star Wars, Warner Bros., Turner, Coca-Cola, Universal, Fortnite, а также создает коллаборации с блогерами (Влад Бумага А4, Anastasiz, Rahim Abramov, JOVE, Belovme, ВПШ), и музыкальными исполнителями (Fogel, Artik & Asti, Elvira T).
        </div>
        <div class="text__desc">
          ТВОЕ – это качественная одежда, доступная для всех. ТВОЕ – это стильные вещи трендовых фасонов и разнообразных цветов. ТВОЕ – это вдохновение любимыми героями и яркий акцент в любом образе. ТВОЕ – это твой любимый магазин!
        </div>
        <button>Подробности
          <div class="pulse"></div>
        </button>
      </div>
      <img src="https://tvoe.ru/upload/iblock/ec0/7v418kaakmvijkb4ca3oelk3tt3ono0j.jpeg" alt="#">
    </div>
  </div>
</template>

<script>
export default {
  name: 'AboutCompany',
  // data: () => ({
  //   animatePulse: false
  // }),
  // methods: {
  //   pulse() {
  //     this.animatePulse = true
  //   },
  //   buttonBack() {
  //     this.animatePulse = false
  //   }
  // }
}
</script>

<style scoped>
.wrapper {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  padding: 0 30px;
}

a {
  text-transform: uppercase;
  color: #999;
  text-decoration: none;
  font-size: 10px;
  padding-bottom: 10px;
}

.wrap {
  display: flex;
}

.text {
  text-align: start;
  max-width: 600px;
  margin-right: 140px;
}

.text__title {
  color: #333;
  font-size: 32px;
  font-weight: bold;
  padding-bottom: 35px;
}

.text__desc {
  color: #777;
  padding-bottom: 30px;
  line-height: 1.6;
  font-size: 15px;
}

img {
  max-width: 480px;
  width: 100%;
  padding-top: 15px;
}

button {
  background-color: #272727;
  border: none;
  border-radius: 3px;
  padding: 15px 25px 14px;
  text-transform: uppercase;
  color: #fff;
  font-size: 11px;
  cursor: pointer;
  position: relative;
  overflow: hidden;
}

.pulse {
  position: absolute;
  top: 0;
  left: 0;
  width: 150px;
  height: 150px;
}
.pulse:hover {
  animation: pulse 0.5s ease-out;
}

/* button:hover {
  background-color: #333;
  transition-duration: .5s;
} */

@keyframes pulse {
  from {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    background-color: #999;
    opacity: 0.5;
    transform: scale(2);
  }
  to {
    background-color: #fff;
    opacity: 0;
  }
}

</style>