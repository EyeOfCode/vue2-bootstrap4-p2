<template>
  <div class="carousel-wrapper" v-if="isReady">
    <owl-carousel
      class="owl-theme"
      :items="3"
      :margin="20"
      :loop="true"
      :autoplay="true"
      :nav="false"
      :dots="true"
      :dotsEach="true"
      :autoplayHoverPause="true"
      :autoplayTimeout="6000"
      :smartSpeed="3000"
      :responsive="{
        0: {
          items: 1,
        },
        768: {
          items: 3,
        },
        1024: {
          items: 4,
        },
      }"
      ref="blogCarousel"
      @initialized="handleInitialized"
    >
      <div class="item w-100" v-for="(item, index) in items" :key="index">
        <BlogCard
          :title="item.title"
          :description="item.description"
          :date="item.date"
          :images="item.images"
          :keyIndex="index"
        />
      </div>
    </owl-carousel>
  </div>
</template>

<script>
import 'owl.carousel/dist/assets/owl.carousel.css';
import 'owl.carousel/dist/assets/owl.theme.default.css';
import OwlCarousel from 'vue-owl-carousel';
import BlogCard from './common/BlogCard.vue';

export default {
  name: 'BlogCarousel',
  components: {
    'owl-carousel': OwlCarousel,
    BlogCard,
  },
  props: {
    items: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      isReady: false,
      carouselInstance: null,
    };
  },
  mounted() {
    this.$nextTick(() => {
      this.isReady = true;
    });
  },
  methods: {
    handleInitialized(event) {
      this.carouselInstance = event;
      setTimeout(() => {
        window.dispatchEvent(new Event('resize'));
      }, 300);
    },
  },
  beforeDestroy() {
    if (this.carouselInstance) {
      this.carouselInstance.destroy();
    }
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
