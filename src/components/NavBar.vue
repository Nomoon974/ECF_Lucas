<template>
  <div id="header-wrapper">
    <div class="container">

      <!-- Header -->
      <header id="header">
        <div class="inner">

          <!-- Logo -->
          <router-link to="/"><h1>Magic</h1></router-link>

          <!-- Nav -->
          <nav id="nav">
            <ul>
              <router-link to="/"><li class="current_page_item">Home</li></router-link>
              <router-link to="/collection"><li class="current_page_item">Ma Collection</li></router-link>
            </ul>
          </nav>

        </div>
      </header>

    </div>
  </div>
</template>

<script>
require('@/assets/css/main.css')
require('@/assets/css/card-list.css')

export default {
  name: "NavBar.vue"
}
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css?family=Open+Sans:400,400italic,700,800");
@import '@/assets/css/main.css';
@import '@/assets/css/card-list.css';

</style>