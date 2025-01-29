<template>
  <div>
    <div class="top-0 w-100 fixed-top">
      <TopHeader />
      <SubHeader />
    </div>
    <div class="container" style="margin-top: 155px">
      <slot />
    </div>
    <Footer />
  </div>
</template>

<script>
import TopHeader from '@/components/common/TopHeader.vue';
import SubHeader from '@/components/common/SubHeader.vue';
import Footer from '@/components/common/Footer.vue';

export default {
  components: {
    TopHeader,
    SubHeader,
    Footer,
  },
};
</script>
