<template>
  <div class="card">
    <div
      v-if="badgeTop.name"
      class="header-card"
      :style="{ alignItems: badgeTop.align }"
    >
      <span :style="{ color: badgeTop.color, backgroundColor: badgeTop.bg }">{{
        badgeTop.name
      }}</span>
    </div>
    <div class="card-header">
      <img
        :style="image.style"
        :src="image.url || require('@/assets/images/cart.jpg')"
        :alt="badgeTop.name"
      />
    </div>
    <div class="card-body py-0 text-center">
      <div class="text-truncate text-body">
        {{ title }}
      </div>
      <div v-if="badge" class="d-flex justify-content-center py-2">
        <div class="text-badge">{{ badge }}</div>
      </div>
    </div>
    <div class="card-footer">
      <div class="row">
        <div class="col-6 footer-text">
          <del v-if="discount">₹{{ discount }}</del>
          <span v-if="price">₹{{ price }}</span>
        </div>
        <div class="col-6 footer-btn">
          <button class="btn btn-success">Add</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CardProduct',
  props: {
    badgeTop: {
      type: Object,
      default: () => ({
        name: null,
        bg: 'transparent',
        align: 'center',
        color: 'black',
      }),
    },
    image: {
      type: Object,
      default: () => ({
        url: null,
        style: {
          width: '100%',
          height: '100%',
          margin: '0 auto',
        },
      }),
    },
    title: {
      type: String,
      required: true,
    },
    badge: {
      type: String,
      default: null,
    },
    price: {
      type: Number,
      required: true,
    },
    discount: {
      type: Number,
      required: true,
    },
  },
};
</script>

<style scoped>
.footer-btn {
  font-size: 15px;
  line-height: 21px;
  font-weight: 500;
  display: flex;
  justify-content: end;
  padding: 5px;
}

.btn-success {
  padding: 4px 15px !important;
  height: 28px;
  display: flex;
  align-items: center;
  background-color: #1a8139;
}

.footer-text {
  display: flex;
  white-space: nowrap;
  align-items: center;
  gap: 0.5rem;
  padding: 5px;

  del {
    font-size: 13px;
    color: gray;
  }

  span {
    font-size: 16px;
    font-weight: bolder;
  }
}

.header-card {
  position: absolute;
  z-index: 1;

  span {
    border-top-left-radius: 5px;
    border-bottom-left-radius: 0;
    border-bottom-right-radius: 10px;
    font-size: 13px;
    padding: 5px 10px;
    font-weight: 600;
  }
}

.text-body {
  font-size: 18px;
  line-height: 30px;
  font-weight: 500;
  color: #2b2b2b;
}

.text-badge {
  font-size: 16px;
  line-height: 1.4;
  border-radius: 100px;
  padding: 1px 12px;
  border: 1px solid #c0c0c0;
  width: max-content;
  color: #919191;
}

.card-header {
  border: 0;
  background: #ffffff;
  border-radius: 5px;
}

.card-body {
  background-color: #ffffff;
}

.card-footer {
  background-color: #fffce9;
  border-bottom-right-radius: 5px !important;
  border-bottom-left-radius: 5px !important;
}

.card {
  border-radius: 5px;
  position: relative;
  width: 100%;
}

.card img {
  width: 100%;
  object-fit: cover;
  border-radius: 5px;
}
</style>
