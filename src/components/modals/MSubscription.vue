<template>
  <div class="wrap-subscribe">
    <h2>Подписка на рассылку</h2>
    <div class="label-input">
      <label  for="input">Email </label>
      <p style="color:red" font-color>*</p>
    </div>
    <input class="wrap-subscribe__input" type="text" id="input">
    <div class="switch">
      <label class="false-switch text" for="checkbox"> Я согласен на 
        <input class="false-switch__input" type="checkbox" id="checkbox">
        <span class="false-switch__round"></span>
        <a href="https://www.google.com/search?q=%D0%BF%D0%BE%D0%BB%D0%B8%D1%82%D0%B8%D0%BA%D0%B0+%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8&oq=gjkbnbrf+&aqs=chrome.1.69i57j0i10i131i433i512j0i10i433i512j46i10i512j0i10i512l4j0i10i131i433i512j0i10i512.2887j0j7&sourceid=chrome&ie=UTF-8">
          обработку персональных данных
        </a> 
      </label>
    </div>
    <!-- <label class="switch"> -->
      <!-- <input type="checkbox"> -->
      <!-- <span class="slider round"></span> -->
    <!-- </label> -->
  </div>
</template>

<script>
export default {
  name: 'MSubscription',
  data: () => ({

  }),
  methods: {
    closeModal() {
      this.$emit('closeWin')
    }
  }
}
</script>

<style scoped>
.wrap-subscribe {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

h2 {
  color: #333;
}

.label-input {
  display: flex;
  align-items: center;
}

p {
  padding-left: 10px;
}

label {
  font-size: 12px;
}

.wrap-subscribe__input {
  width: 340px;
  padding: 13px 17px;
  font-size: medium;
  background-color: #fafafa;
  border: 1px solid #ececec;
  border-radius: 3px;
  color: #383838;
}

/* изменить цвет и границу полня инпут при клике */

.switch {
  display: flex;
  align-items: flex-start;
  margin-top: 35px;
}

.switch:last-of-type {
  color: #999;
}
/* -------------------------------------------------------switch */
.false-switch {
  position: relative;
  display: inline-block;
  width: 30px;
  height: 15px;
}
.false-switch__input {
  display:none;
}
.false-switch__round {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #ccc;
  -webkit-transition: .4s;
  transition: .4s;
}

.false-switch__round:before {
  position: absolute;
  content: "";
  height: 11px;
  width: 11px;
  left: 4px;
  bottom: 2px;
  background-color: white;
  -webkit-transition: .4s;
  transition: .4s;
}

.false-switch__input:checked + .false-switch__round {
  background-color: #2196F3;
}

.false-switch__input:focus + .false-switch__round {
  box-shadow: 0 0 1px #2196F3;
}

input:checked + .false-switch__round:before {
  -webkit-transform: translateX(26px);
  -ms-transform: translateX(26px);
  transform: translateX(12px);
}

.false-switch__round {
  border-radius: 34px;
}

.false-switch__round:before {
  border-radius: 50%;
}


a {
  text-decoration: none;
  color: #1b1a1a;
}
</style>