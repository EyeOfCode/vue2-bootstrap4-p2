<template>
  <div class="card">
    <div class="card-header">
      <ImageCarousel
        :images="images"
        :keyIndex="keyIndex"
        @carousel-initialized="handleImageCarouselInit"
      />
    </div>
    <div class="card-body">
      <div class="text-title">
        {{ title }}
      </div>
      <small class="text-date">{{ date }}</small>
      <div class="text-discretion pt-3">
        {{ description }}
      </div>
    </div>
    <div class="card-footer">
      <a href="#" class="text-link">Read more...</a>
    </div>
  </div>
</template>

<script>
import ImageCarousel from '@/components/common/ImageCarousel.vue';

export default {
  name: 'BlogCard',
  components: {
    ImageCarousel,
  },
  props: {
    title: {
      type: String,
      required: true,
    },
    images: {
      type: Array,
      default: () => [require('@/assets/images/cart.jpg')],
    },
    description: {
      type: String,
      default: null,
    },
    date: {
      type: String,
      default: null,
    },
    keyIndex: {
      type: Number,
      default: null,
    },
  },
  methods: {
    handleImageCarouselInit(event) {
      this.$emit('image-carousel-initialized', event);
    },
  },
};
</script>

<style scoped>
.text-title {
  color: #707070;
  font-weight: 600;
  font-size: 15px;
  word-wrap: break-word;
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  line-clamp: 2;
  -webkit-box-orient: vertical;
  height: 40px;
}

.text-date {
  font-size: 0.875em;
  color: #808080a6;
  font-weight: 600;
  overflow: hidden;
  width: 100%;
  display: -webkit-box;
  -webkit-line-clamp: 1;
  -webkit-box-orient: vertical;
}

.text-discretion {
  overflow: hidden;
  width: 100%;
  display: -webkit-box;
  -webkit-line-clamp: 4;
  -webkit-box-orient: vertical;
  height: 100px;
}

.text-link {
  color: #209244;
  text-decoration: underline;
  font-size: 14px;
}

.card-header {
  border: 0;
  background: #ffffff;
  border-radius: 5px;

  img {
    max-height: 180px;
    object-fit: cover;
    width: 100%;
    border-radius: 20px;
  }
}

.card-body {
  padding-top: 0 !important;
  background-color: #ffffff;
}

.card-footer {
  border: 0;
  background-color: #ffffff;
  border-bottom-right-radius: 5px !important;
  border-bottom-left-radius: 5px !important;
}
</style>
