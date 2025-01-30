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
      :autoplayTimeout="6000"
      :responsive="{
        0: {
          items: 2,
        },
        768: {
          items: 5,
        },
      }"
    >
      <div class="item" v-for="(item, index) in items" :key="index">
        <div
          v-if="item.title"
          class="header-card text-center text-content"
          :style="{ backgroundColor: item.color || 'black' }"
        >
          <span>{{ item.title }}</span>
        </div>
        <div class="img-wrapper">
          <img :src="item.image" :alt="item.title" />
          <div class="d-flex align-items-center justify-content-center">
            <del v-if="item.price" class="text-center text-price">
              ₹{{ item.price }}
            </del>
            <span class="text-center text-discount pr-1" v-if="item.discount">
              ₹{{ item.discount }}
            </span>
            <span class="text-center text-weight" v-if="item.weight">
              ({{ item.weight }} g)
            </span>
          </div>
        </div>
        <div
          v-if="item.footer"
          class="footer-card text-center text-content"
          :style="{ backgroundColor: item.color || 'black' }"
        >
          <span class="text-truncate text-footer">{{ item.footer }}</span>
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
  name: 'ProductCarousel',
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

<style>
.text-footer {
  font-size: 18px;
  padding: 10px 0;
}

.text-price {
  font-size: 14px;
  color: #000;
}

.text-weight {
  font-size: 13px;
  color: #000;
}

.text-discount {
  font-size: 24px;
  font-weight: 700;
  color: #000;
}

.text-content {
  color: #fff;
  font-size: 17px;
  padding: 3px;
}

.header-card {
  border-bottom-left-radius: 10px;
  border-bottom-right-radius: 10px;
  position: absolute;
  z-index: 1;
  width: 100%;
}

.footer-card {
  border-bottom-left-radius: 20px;
  border-bottom-right-radius: 20px;
}

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
