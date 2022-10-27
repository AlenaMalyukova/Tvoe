<template>
  <div class="wrap">
    <h2>Выберите город</h2>
    <input 
      list="cities"
      v-model="city"
      placeholder="Введите название города"
    />
    <button class="submit" @click="selectCity"></button>
    <datalist v-if="city" id="cities">
      <option 
        v-for="value of cities" 
        :key="value" 
        :value="value">
      </option>
    </datalist>
  </div>
</template>

<script>
export default {
  name: 'MSelectCity',
  data: () => ({
    city: null,
    cities: [
      'Москва',
      'Волгоград',
      'Воронеж',
      'Сочи',
      'Бобров'
    ]
  }),
  methods: {
    selectCity() {
      if (!this.city) {
        return
      }

      this.$emit('selectCity', this.city)
    },
  }
}
</script>

<style scoped>
.wrap {
  display: flex;
  flex-direction: column;
}
h2 {
  padding-bottom: 15px;
  text-align: start;
}
input {
  width: 340px;
  padding: 13px 17px;
  font-size: medium;
  background-color: #fafafa;
  border: 1px solid #ececec;
  border-radius: 3px;
  color: #383838;
}
.submit {
  position: absolute;
  top: 126px;
  right: 80px;
  max-width: 25px;
  max-height: 25px;
  width: 100%;
  height: 100%;
  border: none;
  cursor: pointer;
  background-color: #fafafa;
  background-image: url(https://img.icons8.com/ios-glyphs/30/737373/search--v1.png);
}
.submit:hover {
  background-image: url(https://img.icons8.com/ios-glyphs/30/1A1A1A/search--v1.png);
}
</style>