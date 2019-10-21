<template>
  <section class="checkout-section">
    <div class="delivery">
      <div class="deliver-left">
        <span class="delivery-time">送达时间</span>
        <div v-if="shopInfo.delivery_mode.text" class="delivery-extra">
          <span>{{shopInfo.delivery_mode.text}}</span>
        </div>
      </div>
      <div class="delivery-right">
        <span class="delivery-select">尽快送达 ({{deliveryTime(shopInfo.order_lead_time)}}送达)</span>
        <i class="fa fa-angle-right"></i>
      </div>
    </div>
    <div class="cart-item">
      <div class="cart-item-title">支付方式</div>
      <div class="pay-text">在线支付</div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Delivery",
  props: {
    shopInfo: Object
  },
  methods: {
    deliveryTime(time) {
      let date = new Date();
      date.setMinutes(date.getMinutes() + time);
      return date.getHours() + ":" + date.getMinutes();
    }
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
.delivery {
  display: flex;
  align-items: center;
  justify-content: space-between;
  border-bottom: 1px dotted #eee;
  padding: 4.266667vw 0;
}
.delivery-left {
  flex: 1;
  display: flex;
  flex-direction: column;
}
.delivery-time {
  font-size: 1rem;
  font-weight: 500;
}
.delivery-extra {
  margin-top: 0.8vw;
  font-size: 0.6rem;
}
.delivery-extra > span {
  display: inline-block;
  word-spacing: 0.666667vw;
  padding: 0.4vw 1.066667vw;
  line-height: 1;
  background-image: linear-gradient(90deg, #0af, #0085ff);
  color: #fff;
  border-radius: 1px;
}
.delivery-right {
  text-align: right;
}
.delivery-select {
  text-align: right;
  color: #2395ff;
}
.delivery-right > i {
  margin-left: 0.666667vw;
  color: #888;
  font-size: 1.2rem;
}
.cart-item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 4.266667vw 0 5.333333vw 0;
  font-size: 1rem;
  color: #333;
}
.cart-item .cart-item-title {
  font-weight: 500;
}
.pay-text {
  color: #2395ff;
}
</style>
