<template>
  <nav v-bind:class="navTheme" class="navbar navbar-expand-lg">
    <a class="navbar-brand" href="#">Navbar</a>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
      <div class="navbar-nav">
        <router-link class="nav-item nav-link" to="/">Home</router-link>
        <router-link class="nav-item nav-link" to="/about">About</router-link>
        <a class="nav-item nav-link" @click="darkToggle ()">Dark</a>
        <a class="nav-item nav-link" @click="lightToggle ()">Light</a>
      </div>
    </div>
  </nav>
  <router-view/>
</template>

<script>

export default {
  name: 'App',
  data () {
    return {
      darkTheme: true
    }
  },
  computed: {
    navTheme: function () {
      return {
        'navbar-light bg-light': this.darkTheme === false,
        'navbar-dark bg-dark': this.darkTheme === true
      }
    }
  },
  methods: {
    darkToggle() {
      this.darkTheme = true
    },
    lightToggle() {
      this.darkTheme = false
    }
  }
}
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

</style>
