<template>
  <div class="layout">
    <div class="layout-content">
      <!-- <Navbar /> -->
      <div class="layout-hero-content">
        <slot />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'layout',
}
</script>

<style lang="scss" scoped>
.layout {
  background-image: url(../assets/home/background-home-desktop.jpg);
  background-size: cover;
  height: 900px;
  color: #fff;
  &-content {
  }
  &-hero-content {
    width: 100%;
  }

  @media screen and (max-width: 768px) {
    background-image: url(../assets/home/background-home-tablet.jpg);
    height: 100vh;
    &-content {
    }
    &-hero-content {
      width: 100%;
      margin: 0;
    }
  }
}
</style>
