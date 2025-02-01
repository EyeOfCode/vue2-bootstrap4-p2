<template>
  <div class="carousel-wrapper">
    <owl-carousel
      class="owl-theme"
      :items="5"
      :margin="20"
      :loop="true"
      :autoplay="true"
      :nav="false"
      :dots="true"
      :dotsEach="true"
      :autoplayHoverPause="false"
      :autoplayTimeout="6000"
      :responsive="{
        0: {
          items: 1,
        },
        768: {
          items: 3,
        },
        1024: {
          items: 5,
        },
      }"
    >
      <div class="item w-100" v-for="item in items" :key="item.title">
        <ProfileCard
          :image="item.image"
          :title="item.title"
          :footer="item.footer"
          :description="item.description"
        />
      </div>
    </owl-carousel>
  </div>
</template>

<script>
import 'owl.carousel/dist/assets/owl.carousel.css';
import 'owl.carousel/dist/assets/owl.theme.default.css';
import OwlCarousel from 'vue-owl-carousel';
import ProfileCard from './common/ProfileCard.vue';

export default {
  name: 'ProfileCarousel',
  components: {
    'owl-carousel': OwlCarousel,
    ProfileCard,
  },
  props: {
    items: {
      type: Array,
      required: true,
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
