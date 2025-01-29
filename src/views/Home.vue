<template>
  <div class="w-100 carousel-promotion">
    <PromotionCarousel :items="slides" />
  </div>
</template>

<script>
import PromotionCarousel from '@/components/common/PromotionCarousel.vue';

export default {
  name: 'Home',
  components: {
    PromotionCarousel,
  },
  data() {
    return {
      slides: [
        {
          image:
            'https://ik.imagekit.io/44y3v51cp/kisankonnect/Images/BannerImage/20241210112748Hurda Combo Story Web.jpg?tr=f-webp',
          title: 'Slide 1',
        },
        {
          image:
            'https://ik.imagekit.io/44y3v51cp/kisankonnect/Images/BannerImage/20250120092708Gajar Halwa Web Story.jpg?tr=f-webp',
          title: 'Slide 2',
        },
        {
          image:
            'https://ik.imagekit.io/44y3v51cp/kisankonnect/Images/BannerImage/20241219162537Story Banner Web  1920px  600px.png?tr=f-webp',
          title: 'Slide 3',
        },
        {
          image:
            'https://ik.imagekit.io/44y3v51cp/kisankonnect/Images/BannerImage/20241210112748Hurda Combo Story Web.jpg?tr=f-webp',
          title: 'Slide 1',
        },
        {
          image:
            'https://ik.imagekit.io/44y3v51cp/kisankonnect/Images/BannerImage/20250120092708Gajar Halwa Web Story.jpg?tr=f-webp',
          title: 'Slide 2',
        },
        {
          image:
            'https://ik.imagekit.io/44y3v51cp/kisankonnect/Images/BannerImage/20241219162537Story Banner Web  1920px  600px.png?tr=f-webp',
          title: 'Slide 3',
        },
        {
          image:
            'https://ik.imagekit.io/44y3v51cp/kisankonnect/Images/BannerImage/20241210112748Hurda Combo Story Web.jpg?tr=f-webp',
          title: 'Slide 1',
        },
        {
          image:
            'https://ik.imagekit.io/44y3v51cp/kisankonnect/Images/BannerImage/20250120092708Gajar Halwa Web Story.jpg?tr=f-webp',
          title: 'Slide 2',
        },
        {
          image:
            'https://ik.imagekit.io/44y3v51cp/kisankonnect/Images/BannerImage/20241219162537Story Banner Web  1920px  600px.png?tr=f-webp',
          title: 'Slide 3',
        },
        // Add more slides as needed
      ],
    };
  },
};
</script>

<style scoped>
.carousel-promotion {
  overflow: hidden;
}
</style>
