<template>
  <section class="checkout-section cart-group">
    <h3>{{orderInfo.shopInfo.name}}</h3>
    <ul>
      <li v-for="(food,index) in orderInfo.selectFoods" :key="index">
        <img :src="food.image_path" alt>
        <div class="cart-group-info">
          <span>{{food.name}}</span>
          <span>x {{food.count}}</span>
          <span>{{food.activity.fixed_price}}</span>
        </div>
      </li>
      <li class="cart-group-total">
        <div>配送费</div>
        <div>¥{{orderInfo.shopInfo.float_delivery_fee}}</div>
      </li>
      <li class="cart-group-total">
        <div class="discounts"></div>
        <div class="subtotal">
          <span>小计 ¥</span>
          <span class="price">{{totalPrice}}</span>
        </div>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  name: "CartGroup",
  props: {
    orderInfo: Object,
    totalPrice: Number
  }
};
</script>

<style scoped>
.checkout-section {
  margin-bottom: 2.133333vw;
  padding: 0 5.333333vw;
  background: #fff;
  box-shadow: 0 0.133333vw 0.266667vw 0 rgba(0, 0, 0, 0.05);
}
.cart-group > h3 {
  padding: 4.266667vw 0;
  color: #333;
  text-overflow: ellipsis;
  white-space: nowrap;
  overflow: hidden;
  font-size: 1.1rem;
  line-height: 1;
  font-weight: 700;
}
.cart-group > ul {
  margin-top: 0.666667vw;
  color: #333;
  font-size: 0.9rem;
}
.cart-group > ul > li {
  display: flex;
  align-items: center;
  width: 100%;
  padding: 3.2vw 0;
  border-bottom: 1px dotted #eee;
  color: inherit;
}
.cart-group > ul > li > img {
  width: 9.6vw;
  height: 9.6vw;
}
.cart-group-info {
  margin-left: 2.133333vw;
  overflow: hidden;
  flex: 9;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.cart-group-total {
  justify-content: space-between;
  padding: 4vw 0 4.8vw !important;
}
.discounts {
  color: #bbb;
}
.subtotal .price {
  font-size: 1.5rem;
  font-weight: 500;
}
</style>
