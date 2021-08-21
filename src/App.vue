<template>
  <Header />
</template>

<script>
import Header from '@/components/Header.vue';

export default {
  name: 'App',
  components: {
    Header,
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 62.5%;
  font-family: "Montserrat", sans-serif;
}

body {
  min-height: 100vh;
}

#app {
  text-align: center;
  min-height: 100%;
  padding: 10% 0 10% 0;

  @media (min-width: $tablet) {
    padding: 5% 20% 5% 20%;
  }
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: $color-text-link;
    }
  }
}
</style>
