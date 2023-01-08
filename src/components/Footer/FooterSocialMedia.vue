<template>
  <div class="footer-bottom-wrap">
    <div class="underline">
      <div class="copyright">
        <span>2022 © Tvoe.ru – Интернет-магазин одежды для тебя</span>
      </div>
      <div class="social-media-wrap">
        <button 
          class="icon" 
          v-for="obj in icon" 
          :key="obj.name"
          @mouseover="obj.current = 'color'"
          @mouseleave="obj.current = 'monochrome'">
          <img class="icon__img" :src="obj[`${obj.current}`]" alt="#">
        </button>
      </div>
      <div class="payment-wrap" >
        <div 
          class="payment" 
          v-for="obj in paymentSystemImg" 
          :key="obj.name">
          <img class="payment__img" :src="obj[`${obj.current}`]" @mouseover="obj.current = 'color'"
          @mouseleave="obj.current = 'monochrome'"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FooterSociaMedia',
  data: () => ({
    icon: [
      {
        name: 'vk',
        monochrome: 'https://img.icons8.com/ios/50/null/vk-circled--v1.png',
        color: 'https://img.icons8.com/color/48/null/vk-circled--v1.png',
        current: 'monochrome'
      },
      {
        name: 'tg',
        monochrome: 'https://img.icons8.com/ios-filled/50/null/telegram.png',
        color: 'https://img.icons8.com/color-glass/48/null/telegram-app.png',
        current: 'monochrome'
      },
      {
        name: 'tt',
        monochrome: 'https://img.icons8.com/external-regular-kawalan-studio/24/null/external-tik-tok-social-media-regular-kawalan-studio.png',
        color: 'https://img.icons8.com/color-glass/48/null/tiktok.png',
        current: 'monochrome'
      }
    ],
    paymentSystemImg: [
      {
        name: 'mastercard',
        monochrome: 'https://img.icons8.com/ios-filled/50/null/mastercard-logo.png',
        color: 'https://img.icons8.com/color/48/null/mastercard-logo.png',
        current: 'monochrome'
      },
      {
        name: 'visa',
        monochrome: 'https://img.icons8.com/ios-filled/50/null/visa.png',
        color: 'https://img.icons8.com/color/48/null/visa.png',
        current: 'monochrome'
      },
      {
        name: 'mir',
        monochrome: 'https://img.icons8.com/ios/50/null/transaction-approved.png',
        color: 'https://img.icons8.com/fluency/48/null/transaction-approved.png',
        current: 'monochrome'
      },
      {
        name: 'apple-pay',
        monochrome: 'https://img.icons8.com/wired/64/null/apple-pay.png',
        color: 'https://img.icons8.com/dusk/64/null/apple-pay.png',
        current: 'monochrome'
      }
    ]
  })
}
</script>

<style scoped>
.footer-bottom-wrap {
  padding: 0 30px 60px;
  border-top: 1px solid #494949;
}

.social-media-wrap {
  margin-top: -160px;
  padding: 40px;
  background-color: #333;
  width: max-content;
}

.icon {
  border-radius: 3px;
  border: solid 1px #494949;
  margin: 0 5px;
  padding: 0;
  width: 40px;
  height: 40px;
  background-color: #333;
  cursor: pointer;
}

.icon__img {
  width: 30px;
  margin: 0 auto;
}

.underline {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 60px 0 0;
}

span {
  display: flex;
  color: #999999;
  font-size: 12px;
}

.payment-wrap {
  display: flex;
}

.payment {
  margin: 0 15px;
}

.payment__img{
  width: 30px;
  height: 30px;
}


</style>