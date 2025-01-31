<template>
  <div class="w-100">
    <div class="carousel-promotion">
      <PromotionCarousel :items="promotions" />
      <div class="outer-container">
        <ProductCarousel :items="products" />
      </div>
    </div>
    <div class="container-box">
      <ServiceBox />
    </div>
    <div class="container-box mt-5">
      <div class="w-100">
        <div class="title text-center">Categories</div>
        <div class="list-container mt-4">
          <div class="list-wrapper">
            <div
              v-for="category in categories"
              :key="category.name"
              class="list-item"
            >
              <CardImage :title="category.name" :image="category.image" />
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="container-box mt-5">
      <div class="title text-center py-5">Today's Friday Mela</div>
      <div class="container w-100">
        <SellCarousel
          :items="productsToday"
          :dots="checkResponsive"
          :mouseDrag="checkResponsive"
          :responsive="{ 0: { items: 1 }, 768: { items: 3 } }"
        />
      </div>
    </div>
    <div class="my-4">
      <img
        src="https://ik.imagekit.io/44y3v51cp/kisankonnect/Images/BannerImage/20240702175644Website-Wide-Banner-1920x202.gif?tr=f-webp"
        alt
      />
    </div>
    <div class="special-content">
      <div class="container-box">
        <div class="title text-center py-5">Moms Kitchen Special</div>
        <div class="w-100">
          <SellCarousel :items="productSpecial" />
        </div>
      </div>
    </div>
    <div class="my-4">
      <img
        src="https://ik.imagekit.io/44y3v51cp/kisankonnect/Images/BannerImage/20250120093323Web Category Banner0.png?tr=f-webp"
        alt
      />
    </div>
    <div class="container-box mt-5">
      <div class="title text-center py-5">Fruits Chunk</div>
      <div class="container w-100">
        <SellCarousel
          :items="productFruit"
          :autoplay="false"
          :dots="checkResponsive"
          :mouseDrag="checkResponsive"
          :responsive="{ 0: { items: 1 }, 768: { items: 3 } }"
        />
      </div>
    </div>
    <div class="container-box">
      <div class="title text-center py-5">Recipes & Blogs</div>
      <div class="w-100 fit-content">
        <BlogCarousel :items="blogs" />
      </div>
      <div class="text-center">
        <a href="#" class="text-link">View All...</a>
      </div>
    </div>
    <div class="container-box">
      <div class="title text-center py-5">Media Coverage</div>
      <div class="w-100 fit-content">
        <BannerCarousel :items="banners" />
      </div>
      <div class="text-center">
        <a href="#" class="text-link">View All...</a>
      </div>
    </div>
    <div class="container-box">
      <div class="title text-center py-5">Kisan Kommunity</div>
      <div class="w-100 fit-content">Profile</div>
      <div class="text-center">
        <a href="#" class="text-link">View All...</a>
      </div>
    </div>
    <div class="container-box">
      <div class="title text-center py-5">Kind Words</div>
      <div class="w-100 fit-content">Image</div>
    </div>
    <div class="container-box">
      <div class="title text-center py-5">Why shop from KisanKonnect?</div>
      <div class="w-100 fit-content">Comment slide</div>
    </div>
  </div>
</template>

<script>
import { mockCategoryMenu } from '@/assets/constants/categoryMenu';
import {
  mockProductData,
  mockProductFruitData,
  mockProductSpecialData,
  mockProductTodayData,
} from '@/assets/constants/productData';
import { mockPromotionData } from '@/assets/constants/promotionData';
import BlogCarousel from '@/components/BlogCarousel.vue';
import CardImage from '@/components/common/CardImage.vue';
import ProductCarousel from '@/components/ProductCarousel.vue';
import PromotionCarousel from '@/components/PromotionCarousel.vue';
import ServiceBox from '@/components/ServiceBox.vue';
import SellCarousel from '@/components/SellCarousel.vue';
import { mockBlogData } from '@/assets/constants/blogData';
import BannerCarousel from '@/components/BannerCarousel.vue';
import { mockBannerData } from '@/assets/constants/bannerData';

export default {
  name: 'Home',
  components: {
    PromotionCarousel,
    ProductCarousel,
    ServiceBox,
    CardImage,
    SellCarousel,
    BlogCarousel,
    BannerCarousel,
  },
  data() {
    return {
      promotions: mockPromotionData,
      products: mockProductData,
      categories: mockCategoryMenu,
      productsToday: mockProductTodayData,
      productSpecial: mockProductSpecialData,
      productFruit: mockProductFruitData,
      blogs: mockBlogData,
      banners: mockBannerData,
      windowWidth: window.innerWidth,
    };
  },
  computed: {
    checkResponsive() {
      return this.windowWidth < 768;
    },
  },
  mounted() {
    window.addEventListener('resize', this.onResize);
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.onResize);
  },
  methods: {
    onResize() {
      this.windowWidth = window.innerWidth;
    },
  },
};
</script>

<style scoped>
.fit-content {
  grid-gap: 0;
  padding: 0 1rem;
}

.text-link {
  color: #209244;
  text-decoration: underline;
  font-size: 18px;
  font-weight: 600;
}

.special-content {
  background: #ffedeb;
}

img {
  width: 100%;
  object-fit: cover;
}

.title {
  font-weight: 700;
  font-size: 2rem;
  line-height: 2.8rem;
}

.list-container {
  display: flex;
  justify-content: center;
}

.list-wrapper {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  justify-content: center;
}

.list-item {
  max-width: 184px;
  flex: 0 0 calc(33.333% - 1rem);
}

.outer-container {
  margin: 15px 30px;
  width: calc(100% - 60px);
}

.carousel-promotion {
  overflow: hidden;
}

@media screen and (min-width: 767px) {
  .list-item {
    max-width: 328px;
    flex: 0 0 calc(20% - 1rem);
  }

  .fit-content {
    padding-left: 200px;
    padding-right: 200px;
  }
}
</style>
