<template>
  <main>
    <div class="content">
      <div class="container">
        <Register></Register>
      </div>
      <Carousel></Carousel>
      <Info></Info>
      <Price></Price>
    </div>
  </main>
</template>

<script>
import Register from '@/components/Register';
import Carousel from '@/components/Carousel';
import Info from '@/components/Info';
import Price from '@/components/Price';
import PriceContent from '@/components/PriceContent';

export default {
  name: 'Main',
  components: {
    Register,
    Carousel,
    Info,
    Price,
  },
};
</script>
<style scoped>
.content {
  padding: 25px 0;
}
</style>
