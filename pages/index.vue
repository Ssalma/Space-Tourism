<template>
  <Layout>
    <div class="hero-content">
      <div class="hero-content-text">
        <p class="small-text">SO, YOU WANT TO TRAVEL TO</p>
        <h3 class="large-text">SPACE</h3>
        <p class="description">
          Let’s face it; if you want to go to space, you might as well genuinely
          go to outer space and not hover kind of on the edge of it. Well sit
          back, and relax because we’ll give you a truly out of this world
          experience!
        </p>
      </div>
      <div class="explore-wrapper">
      <div class="hero-content-explore">
        <h1>EXPLORE</h1>
      </div>

      </div>
    </div>
  </Layout>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.hero-content {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  overflow: hidden;
  padding-right: 50px;
  &-text {
    width: 450px;
    .small-text {
      font-family: 'Barlow Condensed';
      font-weight: 400;
      font-size: 28px;
      line-height: 34px;
      letter-spacing: 4.725px;
      color: #d0d6f9;
      margin: 0;
    }
    .large-text {
      font-family: Bellefair;
      font-weight: 400;
      font-size: 150px;
      line-height: 172px;
      color: #ffffff;
      margin: 24px 0;
    }
    .description {
      font-family: Barlow;
      font-weight: 400;
      font-size: 18px;
      line-height: 32px;
      color: #d0d6f9;
      margin: 0;
    }
  }
  &-explore {
    width: 275px;
    height: 275px;
    border-radius: 50%;
    background: #fff;
    color: #000;
    display: flex;
    justify-content: center;
    align-items: center;
    h1 {
      font-family: Bellefair;
      font-weight: 400;
      font-size: 32px;
      line-height: 37px;
      letter-spacing: 2px;
      color: #0b0d17;
    }
  }
  @media screen and (max-width: 765px) {
    display: grid;
    grid-template-columns: 1fr;
    padding: 0;
    grid-gap: 30px;
    &-text {
      width: 100%;
      padding: 5px;
      .small-text {
        font-size: 16px;
        line-height: 18px;
        text-align: center;
      }
      .large-text {
        font-size: 80px;
        line-height: 100px;
        text-align: center;
        margin: 16px 0;
      }
      .description {
        font-size: 15px;
        line-height: 25px;
        text-align: center;
      }
    }
    .explore-wrapper{
      display: flex;
      justify-content: center;
      align-items: center;
    }
    &-explore {
      margin-top: 80px;
      width: 150px;
      height: 150px;
      h1 {
        font-size: 20px;
        line-height: 22px;
        letter-spacing: 1.25px;
      }
    }
  }
}
</style>

