<template>
  <div class="price">
    <div class="container">
      <h3 class="price_title">選擇最適合您的 Evernote</h3>
      <PriceContent></PriceContent>
      <a class="price_program" href="##">方案比較 →</a>
    </div>
  </div>
</template>
<script>
import PriceContent from '@/components/PriceContent';

export default {
  name: 'Price',
  components: {
    PriceContent,
  },
};
</script>
<style scoped>
.price_title {
  margin: 25px 0;
  text-align: center;
  font-size: 2rem;
}
.price_program {
  display: block;
  width: 100px;
  margin: 35px auto;
  text-align: center;
  color: #00a82d;
}
@media (max-width:1200px) {
  .price{
    padding: 0 20px;
  }
}
@media (max-width:770px) {
  .price_title {
    font-size: 1.5rem;
  }
}
</style>