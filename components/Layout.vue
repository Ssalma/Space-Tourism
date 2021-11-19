<template>
  <div class="layout">
    <div class="layout-content">
      <Navbar />
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
    padding-left: 55px;
  }
  &-hero-content {
    width: 87%;
    margin: 250px auto 0;
  }

  @media screen and (max-width: 768px) {
    background-image: url(../assets/home/background-home-tablet.jpg);
    height: 100vh;
    &-content {
      padding: 0 24px;
    }
    &-hero-content {
      width: 100%;
      margin: 0;
    }
  }
}
</style>
