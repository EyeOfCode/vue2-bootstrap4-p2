<template>
  <div class="w-100">
    <div class="carousel-promotion">
      <PromotionCarousel :items="promotions" />
      <div class="outer-container">
        <ProductCarousel :items="products" />
      </div>
    </div>
    <div class="container">
      <ServiceBox />
    </div>
    <div
      class="container mt-5 d-flex justify-content-center align-items-center"
    >
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
    <div
      class="container mt-5 d-flex justify-content-center align-items-center"
    >
      <div class="w-100">
        <div class="title text-center">Today's Friday Mela</div>
        <div class="list-container mt-4">
          <div class="list-wrapper">
            <div
              v-for="product in productsToday"
              :key="product.title"
              class="list-item"
            >
              <CardProduct
                :badge="product.badge"
                :badge-top="product.badgeTop"
                :discount="product.discount"
                :image="product.image"
                :price="product.price"
                :title="product.title"
              />
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="my-4">
      <img
        src="https://ik.imagekit.io/44y3v51cp/kisankonnect/Images/BannerImage/20240702175644Website-Wide-Banner-1920x202.gif?tr=f-webp"
        alt
      />
    </div>
    <div class="special-content">
      <div class="container">
        <div class="title text-center py-5">Today's Friday Mela</div>
        <div>test</div>
      </div>
    </div>
  </div>
</template>

<script>
import { mockCategoryMenu } from '@/assets/constants/categoryMenu';
import {
  mockProductData,
  mockProductTodayData,
} from '@/assets/constants/productData';
import { mockPromotionData } from '@/assets/constants/promotionData';
import CardImage from '@/components/common/CardImage.vue';
import CardProduct from '@/components/common/CardProduct.vue';
import ProductCarousel from '@/components/ProductCarousel.vue';
import PromotionCarousel from '@/components/PromotionCarousel.vue';
import ServiceBox from '@/components/ServiceBox.vue';

export default {
  name: 'Home',
  components: {
    PromotionCarousel,
    ProductCarousel,
    ServiceBox,
    CardImage,
    CardProduct,
  },
  data() {
    return {
      promotions: mockPromotionData,
      products: mockProductData,
      categories: mockCategoryMenu,
      productsToday: mockProductTodayData,
    };
  },
};
</script>

<style scoped>
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
  flex: 0 0 calc(33.333% - 1rem);
}

@media screen and (min-width: 767px) {
  .list-item {
    flex: 0 0 calc(20% - 1rem);
  }
}

.outer-container {
  margin: 15px 30px;
  width: calc(100% - 60px);
}

.carousel-promotion {
  overflow: hidden;
}
</style>
