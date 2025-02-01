<template>
  <div class="carousel-wrapper">
    <owl-carousel
      class="owl-theme"
      :items="5"
      :margin="30"
      :loop="true"
      :autoplay="true"
      :nav="false"
      :dots="true"
      :dotsEach="true"
      :autoplayHoverPause="false"
      :autoplayTimeout="3000"
      :responsive="{
        0: {
          items: 1,
        },
        768: {
          items: 5,
        },
      }"
    >
      <div class="item w-100" v-for="item in items" :key="item.title">
        <CardImage
          :title="item.title"
          :image="item.image"
          :style-title="item.styleTitle"
          :style-image="item.styleImage"
        />
      </div>
    </owl-carousel>
  </div>
</template>

<script>
import 'owl.carousel/dist/assets/owl.carousel.css';
import 'owl.carousel/dist/assets/owl.theme.default.css';
import OwlCarousel from 'vue-owl-carousel';
import CardImage from './common/CardImage.vue';

export default {
  name: 'BannerCarousel',
  components: {
    'owl-carousel': OwlCarousel,
    CardImage,
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
  width: 100%;
  position: relative;
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
  border-bottom-left-radius: 10px;
  border-bottom-right-radius: 10px;
}

.item img {
  width: 100%;
  height: auto;
}

.owl-dots {
  position: relative;
  margin-top: 20px !important;
  display: block !important;
}

.owl-dot span {
  margin: 5px !important;
}

.owl-dot.active span {
  background: #27a84a !important;
  width: 12px !important;
  height: 12px !important;
}

.owl-dot:hover span {
  background: #27a84a !important;
  width: 12px !important;
  height: 12px !important;
}
</style>
