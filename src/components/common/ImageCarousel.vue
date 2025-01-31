<template>
  <div class="carousel-wrapper" v-if="isReady">
    <owl-carousel
      class="owl-theme"
      :items="1"
      :margin="0"
      :nav="false"
      :dots="shouldLoop"
      :dotsEach="shouldLoop"
      :autoplayTimeout="5000"
      :loop="shouldLoop"
      :autoplay="shouldLoop"
      :mouseDrag="shouldLoop"
      :touchDrag="shouldLoop"
      ref="imageCarousel"
      @initialized="handleInitialized"
    >
      <div
        class="item w-100"
        v-for="(image, index) in processedImages"
        :key="index"
      >
        <img :src="image" :alt="'Blog image ' + (index + 1)" />
      </div>
    </owl-carousel>
  </div>
</template>

<script>
import 'owl.carousel/dist/assets/owl.carousel.css';
import 'owl.carousel/dist/assets/owl.theme.default.css';
import OwlCarousel from 'vue-owl-carousel';

export default {
  name: 'ImageCarousel',
  components: {
    'owl-carousel': OwlCarousel,
  },
  props: {
    images: {
      type: Array,
      default: () => [require('@/assets/images/cart.jpg')],
    },
    keyIndex: {
      type: Number,
      default: null,
    },
  },
  data() {
    return {
      isReady: false,
      carouselInstance: null,
    };
  },
  computed: {
    processedImages() {
      return this.images.map((image) => {
        if (typeof image === 'string') {
          if (image.startsWith('/')) {
            return require('@/assets/images/cart.jpg');
          }
          return image;
        }
        return image;
      });
    },
    shouldLoop() {
      return this.processedImages.length > 1;
    },
  },
  mounted() {
    this.$nextTick(() => {
      this.isReady = true;
    });
  },
  methods: {
    handleInitialized(event) {
      this.carouselInstance = event;
      this.$emit('carousel-initialized', {
        index: this.keyIndex,
        instance: event,
      });
    },
  },
  beforeDestroy() {
    if (this.carouselInstance) {
      this.carouselInstance.destroy();
    }
  },
};
</script>

<style scoped>
.carousel-wrapper {
  width: 100%;
  position: relative;
  overflow: hidden;
  border-radius: 5px;
}

.item {
  position: relative;
  width: 100%;
  border-radius: 5px;
  overflow: hidden;
}

.item img {
  width: 100%;
  height: 180px;
  object-fit: cover;
  border-radius: 5px;
  margin-bottom: 25px;
}

::v-deep .owl-dots {
  position: absolute;
  bottom: 0;
  width: 100%;
  margin: 0 !important;
  display: flex !important;
  align-items: center !important;
  justify-content: center !important;
}

::v-deep .owl-dot span {
  margin: 5px !important;
  background: #dbdbdb !important;
  transition: all 0.3s ease;
}

::v-deep .owl-dot.active span {
  background: #27a84a !important;
  width: 12px !important;
  height: 12px !important;
}

::v-deep .owl-dot:hover span {
  background: #27a84a !important;
  width: 12px !important;
  height: 12px !important;
}
</style>
