<template>
  <div class="cart-item" @click="$emit('click')">
    <div class="cart-item-title">{{title}}</div>
    <div class="cart-item-right" v-if="subHead">
      <span>{{subHead}}</span>
      <i class="fa fa-angle-right"></i>
    </div>
  </div>
</template>

<script>
export default {
  name: "CartItem",
  props: {
    title: String,
    subHead: String
  }
};
</script>

<style scoped>
.cart-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 4.266667vw 0;
  font-size: 1rem;
  color: #333;
  border-bottom: 1px dotted #eee;
}
.cart-item-title {
  font-weight: 500;
  flex: none;
}
.cart-item-right {
  display: flex;
  -webkit-align-items: center;
  align-items: center;
  color: #bbb;
  font-size: 0.9rem;
  max-width: 69.333333vw;
}
.cart-item-right > span {
  text-overflow: ellipsis;
  overflow: hidden;
  flex-grow: 1;
  white-space: nowrap;
}
.cart-item-right > i {
  font-size: 1.2rem !important;
  margin-left: 5px;
}
</style>
