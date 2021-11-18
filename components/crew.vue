<template>
  <div class="crew">
    <div class="crew-content">
      <div class="crew-content-text">
        <h2 class="page-title"><span>02</span>MEET YOUR CREW</h2>
        <p class="title">{{ crew.title }}</p>
        <p class="name">{{ crew.name }}</p>
        <p class="description">{{ crew.description }}</p>
      </div>
      <div class="image-wrapper">
        <img :src="crew.image" alt="" class="crew-image" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'crew',
  props: {
    crew: {
      type: Object,
      required: true,
    },
  },
}
</script>

<style lang="scss" scoped>
.crew {
  &-content {
    &-text {
      .page-title {
        font-family: 'Barlow Condensed';
        font-weight: 400;
        font-size: 28px;
        line-height: 34px;
        letter-spacing: 4.725px;
        text-transform: uppercase;
        color: #ffffff;
        margin-bottom: 150px;
        span {
          opacity: 0.25;
          margin-right: 24px;
        }
      }
      .title {
        font-family: Bellefair;
        font-style: normal;
        font-weight: normal;
        font-size: 32px;
        line-height: 37px;
        text-transform: uppercase;
        color: #ffffff;
        mix-blend-mode: normal;
        opacity: 0.5;
      }
      .name {
        font-family: Bellefair;
        font-style: normal;
        font-weight: normal;
        font-size: 56px;
        line-height: 64px;
        text-transform: uppercase;
        color: #ffffff;
        margin: 13px 0 29px 0;
      }
      .description {
        font-family: Barlow;
        font-style: normal;
        font-weight: normal;
        font-size: 18px;
        line-height: 32px;
        color: #d0d6f9;
        max-width: 430px;
      }
      .btn-container {
        .btn {
          width: 15px;
          height: 15px;
          background: #ffffff;
          border-radius: 50%;
          border: none;
          span {
            opacity: 0;
          }
        }
      }
    }
    .crew-image {
      height: 680px;
    }
  }
  @media screen and (max-width: 768px) {
    &-content {
      &-text {
        text-align: center;
        .page-title {
          position: absolute;
          top: 0;
          font-size: 16px;
          line-height: 19px;
          left: 90px;
          span{
            font-weight: 700;
            margin-right: 16px;
          }
          // margin-bottom: 32px;
        }
        .title {
          margin-top: 32px;
          font-size: 16px;
          line-height: 18px;
        }
        .name {
          font-size: 24px;
          line-height: 27px;
        }
        .description {
          font-size: 15px;
          line-height: 25px;
        }
      }
      .image-wrapper {
        border-bottom: 1px solid #383b4b;
        margin: 50px 0;
        width: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
      }
      .crew-image {
        max-width: 225px;
        height: 250px;
      }
    }
  }
}
</style>