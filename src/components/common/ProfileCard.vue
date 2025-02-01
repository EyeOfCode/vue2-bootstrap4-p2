<template>
  <div class="card">
    <div class="card-header">
      <img :src="image" :alt="title" />
    </div>
    <div class="card-body">
      <div>{{ title }}</div>
      <div>{{ description }}</div>
      <div>{{ footer }}</div>
      <div class="w-100">
        <button class="btn btn-success w-100">View My Story</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProfileCard',
  props: {
    image: {
      type: String,
      default: () => require('@/assets/images/cart.jpg'),
    },
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    footer: {
      type: String,
      required: true,
    },
  },
};
</script>

<style scoped>
.card {
  background: #fffcec 0% 0% no-repeat padding-box !important;
  box-shadow: 0 3px 6px #00000029 !important;
  border-radius: 15px !important;
  opacity: 1 !important;
  border: 2px solid #9acfb3 !important;
  cursor: pointer;
  margin-bottom: 30px;
  margin: 62px 0 25px !important;
  padding: 5px 10px !important;
  text-align: center !important;
}

.card-header {
  border: 0;
  background: transparent !important;
  border-radius: 5px !important;
  border-bottom: 0px !important;

  img {
    border-radius: 100%;
    object-fit: cover;
    margin-top: -80px;
    border: 2px solid #9acfb3;
    display: initial !important;
    width: 128px !important;
    position: relative;
  }
}

.card-body {
  padding-top: 0 !important;
}
</style>
