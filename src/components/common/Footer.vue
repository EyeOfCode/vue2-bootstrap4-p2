<template>
  <footer class="footer pt-5">
    <div class="mx-5 row">
      <div class="col-12 col-sm-4 col-md-3 col-lg-2">
        <img
          style="max-width: 139px; position: relative; bottom: 27px"
          src="@/assets/images/Kisankonnect_logo_footer.png"
          alt="kisankonnect-logo"
        />
      </div>
      <div class="col-lg-2 col-sm-4 footer_menu_div">
        <div>Menu</div>
        <ul class="footer_menu">
          <li>Home</li>
          <li>Categories</li>
          <li>My Cart</li>
          <li>Profile</li>
        </ul>
      </div>
      <div class="col-lg-5 col-sm-4 footer_menu_div">
        <div>Contacts</div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
};
</script>

<style scoped>
.footer_menu {
  list-style: none;
  position: relative;
  border: 0 none;
  margin: 0;
  padding: 0;
}
.footer_menu li {
  padding: 3px 0;
}
.footer_menu_div {
  position: relative;
}
.footer_menu_div:before {
  content: '';
  min-height: 90%;
  position: absolute;
  left: -10px;
  top: 33px;
  display: block;
}
</style>
