<template>
  <div class="home">
    <h1 class="title">{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'MainPage',
  props: {
    msg: String,
  },
};
</script>

<style scoped lang="scss">
.title {
  font-size: $font-size-m;
  transition: $transition;

  @media (min-width: $tablet) {
    font-size: $font-size-l;
  }
}
</style>
