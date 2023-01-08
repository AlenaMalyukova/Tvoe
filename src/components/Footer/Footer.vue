<template>
  <div class="wrap-footer">
    <div class="footer">
      <div class="links-wrap">
        <FooterLinks title='Компания' :links='linksCompany'/>
        <FooterLinks title='Информация' :links='linksInfo'/>
      </div>
      <div class="support">
        <button class="subscription" @click="openModal">
          <div class="subscription-items">
            <span>Подписаться на рассылку</span> 
            <div class="subscription-items__img"></div>
          </div>
        </button>
        <button class="phone">8 (800) 555-5696</button>
      </div>
    </div>
    <FooterSocialMedia/>
    <ModalWindow 
      v-if="isModalVisible"
      @closeWin="closeModal">
      <template v-slot:content>
        <MSubscription/>
      </template>
    </ModalWindow>
  </div>
</template>

<script>
import FooterLinks from './FooterLinks'
import MSubscription from '../modals/MSubscription'
import FooterSocialMedia from './FooterSocialMedia'
import ModalWindow from '../ui/ModalWindow'

export default {
  name: 'Footer',
  components: {
    FooterLinks,
    MSubscription,
    FooterSocialMedia,
    ModalWindow
  },
  data: () => ({
    isModalVisible: false,
    linksCompany: [
      {
        name: 'О компании',
        link: 'https://tvoe.ru/company/'
      },
      {
        name: 'Новости',
        link: 'https://tvoe.ru/company/news/'
      },
      {
        name: 'Работа у нас',
        link: 'https://tvoe.ru/company/vacancy/'
      },
      {
        name: 'Контакты',
        link: 'https://tvoe.ru/contacts/'
      },
      {
        name: 'Оптовая торговля',
        link: 'https://tvoe.ru/company/partners/'
      },
      {
        name: 'Карта рассрочки',
        link: 'https://tvoe.ru/halva/'
      },
      {
        name: 'Подарочные карты',
        link: 'https://tvoe.ru/giftcards/'
      },
      {
        name: 'ТВОЕ CLUB',
        link: 'https://tvoe.ru/tvoeloyalty/'
      },
      {
        name: 'Аренда торговых помещений',
        link: 'https://tvoe.ru/arenda/'
      }
    ],
    linksInfo: [
      {
        name: 'Магазины',
        link: 'https://tvoe.ru/contacts/'
      },
      {
        name: 'Условия оплаты',
        link: 'https://tvoe.ru/info/payment/'
      },
      {
        name: 'Условия доставки',
        link: 'https://tvoe.ru/info/delivery/'
      },
      {
        name: 'Возврат',
        link: 'https://tvoe.ru/info/vozvrat/'
      },
      {
        name: 'Политика конфиденциальности',
        link: 'https://tvoe.ru/include/licenses_detail.php'
      },
    ]
  }),
  methods: {
    openModal() {
      this.isModalVisible = true
      console.log(this.isModalVisible)
    },
    closeModal() {
      this.isModalVisible = false
      console.log(this.isModalVisible)
    }
  }
}
</script>

<style scoped>
.wrap-footer {
  background-color: #333;
  padding: 55px 0 10px;
}
.footer {
  display: flex;
  justify-content: space-around;
  padding-bottom: 60px;
}

.links-wrap {
  display: flex;
  justify-content: space-evenly;
  width: 60%;
}

.support {
  display: flex;
  flex-direction: column;
}

.subscription {
  background-color: #494949;
  border: none;
  border-radius: 3px;
  padding: 8px 20px;
  cursor: pointer;
}

.subscription:hover {
  background-color: #363636;
}

.subscription:hover .subscription-items__img {
  background-image: url(https://img.icons8.com/external-kiranshastry-lineal-kiranshastry/64/737373/external-paper-plane-interface-kiranshastry-lineal-kiranshastry.png);
}

.subscription-items {
  display: flex;
  align-items: center;
}

span {
  text-transform: uppercase;
  font-size: 11px;
  color: #fff;
  margin-right: 45px;
  pointer-events: none;
}

.subscription-items__img {
  background-image: url(https://img.icons8.com/external-kiranshastry-lineal-kiranshastry/64/272727/external-paper-plane-interface-kiranshastry-lineal-kiranshastry.png);
  background-repeat: no-repeat;
  background-size: 30px;
  background-position: 100% 50%;
  height: 30px;
  width: 30px;
}

.phone {
  max-width: 210px;
  margin-top: 20px;
  background-color: inherit;
  border: none;
  border-radius: 3px;
  color: #fff;
  background-image: url(https://img.icons8.com/fluency-systems-filled/48/999999/null/phone.png);
  background-repeat: no-repeat;
  background-position: left;
  background-size: 20px;
  padding: 15px 5px;
  cursor: pointer;
  padding-left: 35px;
  text-align: left;
  font-size: 20px;
}

.phone:hover {
  background-color: #fff;
  color: #333;
}

.phone:hover {
  background-image: url(https://img.icons8.com/fluency-systems-filled/48/333333/null/phone.png);
}




</style>