<template>
  <header class="header">
    <nav id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </nav>
    <div class="header__background"></div>
  </header>
  <router-view />
</template>

<script>
export default {
  name: 'Header',
};
</script>

<style scoped lang="scss">
.header {
  @media (min-width: $tablet) {
  }

  &__background {
    height: 250px;
    background-image: url("../assets/image-hero-mobile.jpg");
    background-repeat: no-repeat, no-repeat;
    background-size: 100%;
  }
}
</style>
