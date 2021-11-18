<template>
  <div class="moon">
    <p class="destination">EUROPA</p>
    <p class="description">
      The smallest of the four Galilean moons orbiting Jupiter, Europa is a
      winter lover’s dream. With an icy surface, it’s perfect for a bit of ice
      skating, curling, hockey, or simple relaxation in your snug wintery cabin.
    </p>
    <div class="distance-container">
      <div class="distance-content">
        <p class="average-distance">AVG. DISTANCE</p>
        <p class="distance">628 MIL. km</p>
      </div>
      <div class="distance-content">
        <p class="average-distance">EST. TRAVEL TIME</p>
        <p class="distance">3 YEARS</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.moon {
  .destination {
    font-family: Bellefair;
    font-weight: 400;
    font-size: 100px;
    line-height: 115px;
    color: #ffffff;
    text-transform: uppercase;
    margin: 0;
  }
  .description {
    font-family: Barlow;
    font-style: normal;
    font-weight: normal;
    font-size: 18px;
    line-height: 32px;
    color: #d0d6f9;
    padding-bottom: 54px;
    border-bottom: 1px solid #383b4b;
    margin: 0;
  }
  .distance-container {
    display: flex;
    justify-content: space-between;
    margin-top: 28px;
    .distance-content {
      .average-distance {
        font-family: Barlow Condensed;
        font-style: normal;
        font-weight: normal;
        font-size: 14px;
        line-height: 17px;
        letter-spacing: 2.3625px;
        text-transform: uppercase;
        color: #d0d6f9;
      }
      .distance {
        font-family: Bellefair;
        font-style: normal;
        font-weight: normal;
        font-size: 28px;
        line-height: 32px;
        text-transform: uppercase;
        color: #ffffff;
      }
    }
  }
  @media screen and (max-width: 800px) {
    .destination {
      font-size: 56px;
      line-height: 64px;
      padding: 20px 0;
    }
    .description {
      font-size: 15px;
      line-height: 25px;
      padding-bottom: 32px;
    }
    .distance-container {
      flex-direction: column;
      .distance-content{
        margin-bottom: 32px;
        .distance{
          padding-top: 12px;
        }

      }
    }
  }
}
</style>