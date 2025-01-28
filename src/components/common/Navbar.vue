<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <a class="navbar-brand" href="#">Vue 2 Template</a>
    <button
      class="navbar-toggler"
      type="button"
      data-toggle="collapse"
      data-target="#navbarNav"
      aria-controls="navbarNav"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav" @click="closeMenu">
      <ul class="navbar-nav">
        <li class="nav-item">
          <router-link class="nav-link" to="/" exact-active-class="active">
            Home
          </router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link" to="/about" active-class="active">
            About
          </router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link" to="/user" active-class="active">
            User
          </router-link>
        </li>
      </ul>
    </div>
  </nav>
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
.active {
  border-bottom: 2px solid green;
  padding-bottom: 2px;
}
.nav-link:hover {
  border-bottom: 2px solid gray;
  padding-bottom: 2px;
}
</style>
