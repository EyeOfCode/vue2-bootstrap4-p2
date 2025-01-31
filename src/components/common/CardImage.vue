<template>
  <div class="d-flex flex-column justify-content-center align-items-center">
    <div class="card w-100">
      <div class="card-body p-0 w-100">
        <img :src="image || require('@/assets/images/cart.jpg')" :alt="title" />
      </div>
    </div>
    <div class="py-3 text-center" :style="styleTitle">{{ title }}</div>
  </div>
</template>

<script>
export default {
  name: 'CardImage',
  props: {
    title: {
      type: String,
      required: true,
    },
    styleTitle: {
      type: Object,
      default: () => ({
        fontSize: '1.3rem',
        fontWeight: '500',
        lineHeight: '1.4',
      }),
    },
    image: {
      type: String,
      default: null,
    },
  },
};
</script>

<style scoped>
.card {
  border-radius: 1rem;
  box-shadow: #63636333 0 2px 8px;
  display: flex;
  align-items: center;
}

.card img {
  width: 100%;
  object-fit: cover;
  border-radius: 1rem;
  box-shadow: #63636333 0 2px 8px;
  min-height: 115px;
}

@media screen and (min-width: 767px) {
  .card img {
    object-fit: contain;
    max-height: 200px;
  }
}
</style>
