<template>
  <div class="bg-white border-bottom">
    <div class="my-1 d-md-flex align-items-center justify-content-between">
      <div class="d-flex align-items-center">
        <div>
          <img
            class="logo-img"
            src="@/assets/images/kisankonnect_logo.svg"
            alt="logo"
          />
        </div>
        <div class="mx-4 search-group">
          <div class="input-group">
            <div class="input-group-prepend">
              <span class="input-group-text bg-white">
                <i class="fa fa-search"></i>
              </span>
            </div>
            <input
              type="text"
              class="form-control border-left-0"
              id="homeSearch"
              placeholder="Search for Product"
              aria-label="Search"
            />
          </div>
        </div>
        <div class="d-block d-md-none cursor-pointer">
          <div class="d-flex align-items-center justify-content-center">
            <img
              src="@/assets/icons/cart_icon.svg"
              style="height: 32px"
              alt="cart"
            />
          </div>
        </div>
      </div>
      <div class="d-flex align-items-center justify-content-center mr-md-5">
        <div class="mr-3">
          <MenuTitle
            title="Change Category"
            menuName="Categories"
            :menuItems="categoryMenuItems"
          />
        </div>
        <div class="mr-5">
          <MenuTitle
            title="Change Location"
            menuName="Pune"
            :menuItems="puneMenuItems"
          />
        </div>
        <div class="d-none d-md-block mr-4 cursor-pointer">
          <div class="d-flex align-items-center justify-content-center">
            <img
              src="@/assets/icons/cart_icon.svg"
              style="height: 32px"
              alt="cart"
            />
          </div>
          <span class="text-sub-menu">My Cart</span>
        </div>
        <div class="cursor-pointer icon-profile">
          <img src="@/assets/icons/profile_icon.png" alt="user" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import MenuTitle from './MenuTitle.vue';
import { mockCategoryMenu } from '@/assets/constants/categoryMenu';
import { mockPuneMenu } from '@/assets/constants/puneMenu';

export default {
  name: 'SubHeader',
  data() {
    return {
      categoryMenuItems: mockCategoryMenu,
      puneMenuItems: mockPuneMenu,
    };
  },
  components: {
    MenuTitle,
  },
};
</script>

<style scoped>
.icon-profile {
  background: #f0f0f0;
  border-radius: 6px;
  max-height: 38px;

  img {
    padding: 6px;
    max-height: 38px;
  }
}
.text-sub-menu {
  font-size: 12px;
  line-height: 20px;
  font-weight: 600;
}
.border-bottom {
  box-shadow: 0 10px 10px #00000014;
  border-bottom-left-radius: 35px;
  border-bottom-right-radius: 35px;
}
.logo-img {
  max-width: 87.5px;
  max-height: 87.46px;
}
.sub-top-header {
  padding-right: 3.5rem;
}
.search-group {
  max-width: 220px;
}
.input-group-text {
  border-radius: 15px 0 0 15px;
}
.form-control {
  border-radius: 0 15px 15px 0;
}
.form-control:focus {
  padding: 0.8rem 2.75rem;
  border-color: #ced4da;
  box-shadow: none;
}
</style>
