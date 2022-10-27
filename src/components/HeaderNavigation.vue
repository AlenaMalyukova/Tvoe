<template>
<div class="nav">
  <div >
    <button class="nav-search">
    </button>
  </div>
  <div>
    <button class="nav-profile"></button>
  </div>
  <div class="cart-wrapper">
    <button class="nav-shopping-cart">
    </button>
    <div class="cart-wrapper__count">
      {{cartCount}}
    </div>
  </div>
</div>
</template>

<script>

export default {
  name: 'HeaderNavigation',
  components: {
  },
  data: () => ({
    cartCount: '0'
  }),
  methods: {
  }
}
</script>



<style scoped>
.nav {
  display: flex;
  height: 42px;
  padding-right: 30px;
  align-items: center;
}
button {
  border: none;
  background-color: white;
  width: 25px;
  height: 25px;
  background-size: contain;
  margin-left: 35px;
  cursor: pointer;
}
.nav-search {
  background-image: url(https://img.icons8.com/ios-glyphs/30/737373/search--v1.png);
}
.nav-search:hover {
  background-image: url(https://img.icons8.com/ios-glyphs/30/1A1A1A/search--v1.png); 
}
.nav-profile {
  background-image: url(https://img.icons8.com/windows/32/737373/user-male-circle.png);
}
.nav-profile:hover {
  background-image: url(https:img.icons8.com/material-outlined/24/000000/user-male-circle.png)
}
.nav-shopping-cart {
  background-image: url(https://img.icons8.com/pastel-glyph/64/737373/shopping-trolley--v2.png);
}
.nav-shopping-cart__counter {
  margin-left: 20px;
}
.nav-shopping-cart:hover {
  background-image: url(https://img.icons8.com/pastel-glyph/64/000000/shopping-trolley--v2.png);
}

.cart-wrapper {
  display: flex;
  align-items: center;
}

.cart-wrapper__count {
  margin-left: 5px;
  padding: 2px 6px;
  background-color: #222;
  color: white;
  border-radius: 50%;
  font-size: 14px;
}
</style>