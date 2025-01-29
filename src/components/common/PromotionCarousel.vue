<template>
  <div class="carousel-wrapper">
    <owl-carousel
      :items="3"
      :margin="10"
      :loop="true"
      :autoplay="true"
      :center="true"
      :nav="false"
      :dots="false"
      :responsive="{
        0: {
          items: 2,
        },
      }"
    >
      <div class="item" v-for="(item, index) in items" :key="index">
        <div class="img-wrapper">
          <img :src="item.image" :alt="item.title" />
        </div>
      </div>
    </owl-carousel>
  </div>
</template>

<script>
import 'owl.carousel/dist/assets/owl.carousel.css';
import 'owl.carousel/dist/assets/owl.theme.default.css';
import OwlCarousel from 'vue-owl-carousel';

export default {
  name: 'PromotionCarousel',
  components: {
    'owl-carousel': OwlCarousel,
  },
  props: {
    items: {
      type: Array,
      required: true,
      default: () => [],
    },
  },
};
</script>

<style scoped>
.carousel-wrapper {
  width: 185vw;
  position: relative;
  left: 50%;
  right: 50%;
  margin-left: -92.5vw;
  margin-right: -92.5vw;
  overflow: hidden;
}

.img-wrapper {
  position: relative;
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.img-wrapper img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.item {
  position: relative;
  width: 100%;
  border-radius: 8px;
}

.item img {
  width: 100%;
  height: auto;
  border-radius: 4px;
}
</style>
