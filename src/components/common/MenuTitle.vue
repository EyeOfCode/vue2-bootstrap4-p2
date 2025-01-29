<template>
  <div class="cursor-pointer text-center">
    <p class="mb-1">{{ title }}</p>
    <div class="text-sub-menu">
      <div class="dropdown">
        <span class="text-sub-menu" id="menuDropdown" data-toggle="dropdown">
          {{ menuName }}
          <img src="@/assets/icons/downarrow.svg" alt="" />
        </span>

        <div class="dropdown-menu menu" aria-labelledby="menuDropdown">
          <div v-for="item in menuItems" :key="item.name">
            <a class="dropdown-item" href="#">{{ item.name }}</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MenuTitle',
  props: {
    title: {
      type: String,
      required: true,
    },
    menuName: {
      type: String,
      required: true,
    },
    menuItems: {
      type: Array,
      required: true,
      validator(value) {
        return value.length > 0 && value.every((item) => item.name);
      },
    },
  },
};
</script>

<style scoped>
.text-sub-menu {
  font-size: 12px;
  line-height: 20px;
  font-weight: 600;
}
.menu.dropdown-menu {
  max-height: 20rem;
  overflow: scroll;
  overflow-x: hidden;
}
.dropdown-menu {
  left: -135px !important;
  min-width: 25rem;
  padding: 0;
  top: 1.4rem !important;
  border: 0;
  border-radius: 0 0 10px 10px;
  box-shadow: 0 5px 6px #00000045;
}
::-webkit-scrollbar {
  width: 6px;
}

::-webkit-scrollbar-track {
  background: #f1f1f1;
}

::-webkit-scrollbar-thumb {
  background: #888;
}

::-webkit-scrollbar-thumb:hover {
  background: #555;
}
.dropdown-item {
  font-size: 14px;
  font-weight: 500;
  color: #212529;
}
.dropdown-item:hover {
  background-color: #e7f7de;
}
</style>
