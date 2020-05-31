<template>
  <header>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <a class="navbar-brand" href="#">NuxtJS</a>
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
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <li class="nav-item">
            <nuxt-link exact active-class="active" class="nav-link" to="/">
              Home
              <span class="sr-only">(current)</span>
            </nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link no-prefetch active-class="active" class="nav-link" to="/users">Users</nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link active-class="active" class="nav-link" to="/about">About</nuxt-link>
          </li>
          <li class="nav-item"></li>
          <li class="nav-item">
            <nuxt-link active-class="active" class="nav-link" to="/login">Login</nuxt-link>
          </li>
          <li class="nav-item" v-if='isAuth'>
            <a class="nav-link" href="#" @click.prevent="logout">Logout</a>
          </li>
        </ul>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  computed: {
    isAuth() {
      return this.$store.getters.isAuth;
    }
  },
  methods: {
    logout() {
      this.$store.dispatch("logout");
    }
  }
};
</script>

