<template>
  <div class="carousel-wrapper">
    <owl-carousel
      class="owl-theme"
      :items="2"
      :margin="30"
      :loop="true"
      :autoplay="autoplay"
      :nav="false"
      :dots="dots"
      :dotsEach="dots"
      :autoplayHoverPause="false"
      :autoplayTimeout="6000"
      :responsive="responsive"
      :mouseDrag="mouseDrag"
    >
      <div class="item w-100" v-for="item in items" :key="item.title">
        <CardProduct
          :badge="item.badge"
          :badge-top="item.badgeTop"
          :discount="item.discount"
          :image="item.image"
          :price="item.price"
          :title="item.title"
        />
      </div>
    </owl-carousel>
  </div>
</template>

<script>
import 'owl.carousel/dist/assets/owl.carousel.css';
import 'owl.carousel/dist/assets/owl.theme.default.css';
import OwlCarousel from 'vue-owl-carousel';
import CardProduct from './common/CardProduct.vue';

export default {
  name: 'SellCarousel',
  components: {
    'owl-carousel': OwlCarousel,
    CardProduct,
  },
  props: {
    items: {
      type: Array,
      required: true,
    },
    autoplay: {
      type: Boolean,
      default: true,
    },
    dots: {
      type: Boolean,
      default: true,
    },
    mouseDrag: {
      type: Boolean,
      default: true,
    },
    responsive: {
      type: Object,
      default: () => ({
        0: {
          items: 1,
        },
        768: {
          items: 2,
        },
        1024: {
          items: 4,
        },
      }),
    },
  },
};
</script>

<style>
.carousel-wrapper {
  width: 100%;
  position: relative;
  overflow: hidden;
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
