<template>
  <div id="app" :class="{'dark-mode': darkMode}">
    <Header />
    <transition name="slide-fade">
      <router-view />
    </transition>
  </div>
</template>

<script>
  import Header from '@/components/Header';
  
  

export default {
  computed: {
    darkMode() {
      return this.$store.state.isDarkModeOn
    }
  },
  components: {
    Header,
  }
}
</script>

<style lang="scss">
@import '@/assets/styles/app.scss';
@import url('https://fonts.googleapis.com/css2?family=Lato:wght@300;400;700&display=swap');

#app {
  font-family: 'Lato', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: #f1ffffff;
  transition: background-color 0.4s ease-in-out, color 1s ease-in-out;
}

#app.dark-mode {
  color: white;
  background-color: #1B2432;
  transition: background-color 0.4s ease-in-out, color 1s ease-in-out;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
