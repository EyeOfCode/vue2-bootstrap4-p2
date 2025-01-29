<template>
  <div class="top-0 w-100">
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
    <div class="bg-white border-bottom">
      <div class="p-2">
        <img
          class="logo-img"
          src="@/assets/images/kisankonnect_logo.svg"
          alt="logo"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Navbar',
  methods: {
    closeMenu() {
      const navbar = document.getElementById('navbarNav');
      navbar.classList.remove('show');
    },
  },
};
</script>

<style scoped>
.border-bottom {
  box-shadow: 0 10px 10px #00000014;
  border-bottom-left-radius: 35px;
  border-bottom-right-radius: 35px;
}
.icon-app {
  max-width: 28px;
}
.logo-img {
  max-width: 90px;
}
.top-header {
  background: #f7f7f7;
  height: 60px;
  padding: 0 3.5rem 0 8.25rem;
  font-weight: 500;
  font-size: 15px;
  color: #262726;

  .text-header {
    border-right: 2px solid #919191;
  }

  .cursor-pointer {
    cursor: pointer;
  }
}
</style>
