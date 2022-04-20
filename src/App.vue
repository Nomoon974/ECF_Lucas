<template>
  <div id="app">
    <nav>
      <nav-bar />
    </nav>
    <router-view/>
    <footer>
      <footer-comp />
    </footer>
  </div>
</template>

<script>
import navBar from "@/components/NavBar";
import footerComp from "@/components/FooterComp";

require('@/assets/css/main.css')
require('@/assets/css/card-list.css')

export default {
  name: 'HomeView',
  components: {
    navBar,
    footerComp
  }
}

</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Open+Sans:400,400italic,700,800");
@import '@/assets/css/main.css';
@import '@/assets/css/card-list.css';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: rebeccapurple;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: white;
  display: inline-block;
}

nav a.router-link-exact-active {
  color: #42b983;
}




</style>
