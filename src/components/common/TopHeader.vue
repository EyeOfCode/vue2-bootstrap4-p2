<template>
  <div
    class="d-md-flex top-header d-none align-items-center justify-content-between"
  >
    <div class="d-flex align-items-center">
      <div class="text-header">
        <div class="px-1 cursor-pointer">Why KisanKonnect?</div>
      </div>
      <div class="text-header">
        <div class="px-1">Download App</div>
      </div>
      <div class="d-flex align-items-center">
        <img
          class="icon-app mx-2"
          src="@/assets/icons/App-store.svg"
          alt="app-store"
        />
        <img
          class="icon-app mx-2"
          src="@/assets/icons/Playstore.svg"
          alt="play-store"
        />
      </div>
    </div>
    <div class="d-flex align-items-center">
      <div class="text-header">
        <div class="px-1 cursor-pointer">About Us</div>
      </div>
      <div class="text-header">
        <div class="px-1 cursor-pointer">Careers@KisanKonnect</div>
      </div>
      <div>
        <div class="px-1 cursor-pointer">Contact Us</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TopHeader',
};
</script>

<style scoped>
.icon-app {
  max-width: 28px;
}
.top-header {
  background: #f7f7f7;
  height: 60px;
  padding: 0 3.5rem 0 7.25rem;
  font-weight: 500;
  font-size: 13px;
  color: #262726;
}
.text-header {
  border-right: 2px solid #919191;
}
</style>
