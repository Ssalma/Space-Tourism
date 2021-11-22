<template>
  <div class="tech">
    <p class="ellipse">{{ technology.ellipses }}</p>
    <h2 class="heading">{{ technology.heading }}</h2>
    <p class="description">{{ technology.description }}</p>
  </div>
</template>

<script>
export default {
  props: {
    technology: {
      type: Object,
      required: true,
    },
  },
}
</script>

<style lang="scss" scoped>
.tech {
  .ellipse {
    font-family: Barlow Condensed;
    font-style: normal;
    font-weight: normal;
    font-size: 16px;
    line-height: 19px;
    letter-spacing: 2.7px;
    color: #d0d6f9;
    text-transform: uppercase;
  }
  .heading {
    font-family: Bellefair;
    font-style: normal;
    font-weight: normal;
    font-size: 56px;
    line-height: 64px;
    color: #ffffff;
    text-transform: uppercase;
    margin: 12px 0 20px 0;
  }
  .description {
    font-family: Barlow;
    font-style: normal;
    font-weight: normal;
    font-size: 18px;
    line-height: 32px;
    color: #d0d6f9;
  }
  @media screen and (max-width: 768px) {
  text-align: center;
    .ellipse {
      font-size: 14px;
      line-height: 17px;
    }
    .heading {
      font-size: 24px;
      line-height: 28px;
    }
    .description {
      font-size: 15px;
      line-height: 25px;
    }
  }
}
</style>