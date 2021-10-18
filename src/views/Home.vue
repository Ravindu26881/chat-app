<template>
  <div class="home">
    <div class="display-3"> Welcome to Quiz</div>
    <div class="display-5"> Choose what you want to know about yourself</div>
    <router-link class="nav-item nav-link" to="/Quiz01">Quiz 01</router-link>
    <router-link class="nav-item nav-link" to="/Quiz02">Quiz 02</router-link>
    <Main />
  </div>
</template>

<script>

export default {
  name: 'Home',
  components: {
  }
}
</script>
