<template>
  <div class="d-flex flex-column justify-content-center align-items-center">
    <div class="card">
      <div class="card-body p-0">
        <img :src="image || require('@/assets/images/cart.jpg')" :alt="title" />
      </div>
    </div>
    <div class="py-3 text-center title-text">{{ title }}</div>
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

.title-text {
  font-size: 1.3rem;
  line-height: 1.4;
  font-weight: 500;
}

.card img {
  width: 100%;
  object-fit: cover;
  border-radius: 1rem;
  box-shadow: #63636333 0 2px 8px;
}
</style>
