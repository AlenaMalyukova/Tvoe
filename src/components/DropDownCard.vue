<template>
  <div class="dropdown-block" >
    <div class="add">
      <div class="add-number">
        <button class="add-number__sign sign-minus" @click="decrease">-</button>
        <span class="add-number__amount">{{ defaultNumber }}</span>
        <button class="add-number__sign" @click="increase">+</button>
      </div>
      <button class="add-to-busket">В корзину
        <div class="add-to-busket__animate"></div>      
      </button>
    </div>
    <!-- <div class="choose-color"></div>
    <div class="choose-size"></div> -->
  </div>
</template>

<script>
export default {
  name: 'DropDownCard',
  data: () => ({
    isDropDown: false,
    defaultNumber: 1
  }),
  methods: {
    decrease() {
      if (this.defaultNumber === 1) {
        return
      } else {
        this.defaultNumber--
      }
    },
    increase() {
      this.defaultNumber++
    }
  }
}
</script>

<style scoped>
.dropdown-block {
  max-width: 255px;
  width: 100%;
  height: max-content;
  background-color: #fff;
  position: absolute;
  bottom: -57px;
  left: 0px;
  box-shadow: -5px 5px 10px 5px #ececec;
}

.add {
  max-height: 56px;
  display: flex;
}

.add-number {
  width: 50%;
  background-color: #fafafa;
  display: flex;
  flex-wrap: nowrap;
  justify-content: space-around;
  align-items: center;
  padding: 16px 0;
}

.add-number:hover {
  color: #333;
}

.add-number__sign {
  color: rgb(173, 173, 173);
  font-size: 20px;
  display: flex;
  justify-content: center;
  align-items: center;
  height: max-content;
}

.add-number__sign:hover {
  color: #333;
}

.sign-minus {
  font-size: 22px;
  /* max-height: 25px; */
  text-align: center;
}

.add-number__amount {
  background-color: #fafafa;
}

button {
  border: none;
  font-size: 15px;
  cursor: pointer;
  text-transform: uppercase;
  text-align: center;
  background-color: #fafafa;
}

.add-to-busket {
  background-color: #7FE175;
  width: 50%;
  font-size: 11px;
}

.add-to-busket__animate {
  display: none;
  border-radius: 50%;
  background-color: #000;
  opacity: 0.5;
  width: 20px;
  height: 20px;
  position: absolute;
  max-width: 127px;
  max-height: 60px;
  overflow: hidden;
}

.add-to-busket:hover {
  background-color: #98e790;
  transition-duration: .5s;
}
</style>