<template>
  <div class="w-100 box-service d-flex align-items-center overflow-auto">
    <div
      class="box-content text-center flex-md-fill flex-shrink-0 item-service p-2 d-flex flex-column justify-content-center align-items-center mx-2"
    >
      <img class="image-logo my-2" src="@/assets/icons/1.png" alt="box-img-1" />
      <span class="text-title">Free Delivery*</span>
      <p class="mb-0 text-description">
        On all orders above
        <br />
        ₹500
      </p>
    </div>
    <div
      class="box-content text-center flex-md-fill flex-shrink-0 item-service p-2 d-flex flex-column justify-content-center align-items-center mx-2"
    >
      <img class="image-logo my-2" src="@/assets/icons/2.png" alt="box-img-1" />
      <span class="text-title">6Hr Shipping*</span>
      <p class="mb-0 text-description">Delivering across Mumbai & Pune</p>
    </div>
    <div
      class="box-content text-center flex-md-fill flex-shrink-0 item-service p-2 d-flex flex-column justify-content-center align-items-center mx-2"
    >
      <img
        class="image-logo my-2"
        src="@/assets/icons/free_shipping.png"
        alt="box-img-1"
      />
      <span class="text-title">Easy Returns</span>
      <p class="mb-0 text-description">
        For items damaged during transit or quality issues
      </p>
    </div>
    <div
      class="box-content text-center flex-md-fill flex-shrink-0 item-service p-2 d-flex flex-column justify-content-center align-items-center mx-2"
    >
      <img class="image-logo my-2" src="@/assets/icons/4.png" alt="box-img-1" />
      <span class="text-title">All Payment Modes</span>
      <p class="mb-0 text-description">
        Cards, UPI, Wallets, Net Banking and COD
      </p>
    </div>
    <div
      class="box-content text-center flex-md-fill flex-shrink-0 p-2 d-flex flex-column justify-content-center align-items-center mx-2"
    >
      <img class="image-logo my-2" src="@/assets/icons/5.png" alt="box-img-1" />
      <span class="text-title">Customer Support</span>
      <p class="mb-0 text-description">
        Between 7am to 10pm, Monday to Saturday
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ServiceBox',
};
</script>

<style scoped>
.box-content {
  width: 181px;
}

.image-logo {
  max-width: 39px;
}

.text-title {
  font-size: 14px;
  line-height: 1.4;
  color: #1a8139;
  font-weight: 600;
}

.text-description {
  font-size: 11px;
  line-height: 1.4rem;
  margin-top: 0.1rem;
  color: #1a8139;
}

.box-service {
  border: 1px solid #26a649;
  border-radius: 10px;
  scroll-behavior: smooth;
  -webkit-overflow-scrolling: touch;
}

.item-service {
  border-right: 1px solid #26a649;
}
</style>
