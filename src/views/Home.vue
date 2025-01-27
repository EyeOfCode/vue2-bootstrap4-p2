<template>
  <div>
    <h1>Home</h1>
    <p>{{ message }}</p>
    <button class="btn btn-primary" @click="changeMessage">
      Change Message
    </button>
  </div>
</template>

<script>
export default {
  computed: {
    message() {
      return this.$store.getters.message;
    }
  },
  methods: {
    changeMessage() {
      this.$store.dispatch('updateMessage', 'Welcome to Vue 2 with Vuex!');
    }
  }
};
</script>
