<template>
  <div class="tech">
    <picture>
      <source
        media="(max-width: 768px)"
        :srcset="imageMobile"
        alt="picture"
        class="mobile-space-image"
      />
      <img :src="image" alt="picture" class="space-image" />
    </picture>
  </div>
</template>

<script>
export default {
  props: {
    image: {
      type: String,
      required: true,
    },
    imageMobile: {
      type: String,
      required: true,
    },
  },
  data: () => ({}),
}
</script>

<style lang="scss" scoped>
.tech {
  .mobile-space-image {
    display: none;
  }
  .space-image {
    width: 100%;

  }
  @media screen and (max-width: 768px) {
    .space-image{
      width: calc(100% + 48px);
      margin-left: -24px;
    }
  }
}
</style>