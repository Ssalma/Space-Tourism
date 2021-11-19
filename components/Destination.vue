<template>
  <div class="hero">
    <div class="hero-container">
      <Navbar />
      <div class="hero-content">
        <div class="hero-content-text">
          <div>
            <h2 class="page-title"><span>01</span> Pick your destination</h2>
            <div class="planet">
              <transition name="image" mode="out-in">
                <img
                  :src="transition[activeTab]"
                  alt=""
                  class="planet-image"
                />
              </transition>
            </div>
          </div>
        </div>
        <div class="hero-content-explore">
          <div class="tabs">
            <button
              v-for="tab in tabs"
              :key="tab"
              :class="['tab-item', activeTab === tab ? 'active' : '']"
              @click="activeTab = tab"
            >
              <Nuxtlink>
                {{ tab }}
              </Nuxtlink>
            </button>
          </div>
          <div class="destination">
            <Moon v-if="activeTab === 'Moon'" />
            <Mars v-if="activeTab === 'Mars'" />
            <Europa v-if="activeTab === 'Europa'" />
            <Titan v-if="activeTab === 'Titan'" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import MoonImg from '../assets/destination/image-moon.png'
import MarsImg from '../assets/destination/image-mars.png'
import EuropaImg from '../assets/destination/image-europa.png'
import TitanImg from '../assets/destination/image-titan.png'

export default {
  name: 'destination',
  data: () => ({
    tabs: ['Moon', 'Mars', 'Europa', 'Titan'],
    activeTab: 'Moon',
    transition: {
      Moon: MoonImg,
      Mars: MarsImg,
      Europa: EuropaImg,
      Titan: TitanImg,
    },
  }),
}
</script>

<style lang="scss" scoped>
.image-enter-active,
.image-leave-active {
  transition: 0.3s ease-out;
}

.image-enter,
.image-leave-to {
  transition: 1s ease-in-out;
}

.hero {
  background-image: url(../assets/destination/background-destination-desktop.jpg);
  height: 900px;
  padding-top: 40px;
  color: #fff;
  overflow: hidden;
  &-container {
    padding-left: 55px;
  }

  &-content {
    display: grid;
    grid-template-columns: 1fr 430px;
    width: 90%;
    margin: 75px auto;
    padding: 0 85px 0 30px;
    z-index: 1;

    &-text {
      .planet {
        margin: 95px 0 0 35px;
      }

      .page-title {
        font-family: 'Barlow Condensed';
        font-weight: 400;
        font-size: 28px;
        line-height: 34px;
        letter-spacing: 4.725px;
        text-transform: uppercase;
        color: #ffffff;

        span {
          opacity: 0.25;
        }
      }
    }

    &-explore {
      margin-top: 110px;

      .tab-item {
        font-family: 'Barlow Condensed';
        font-weight: normal;
        font-size: 16px;
        line-height: 19px;
        letter-spacing: 2.7px;
        color: #d0d6f9;
        background: transparent;
        border: none;
        margin-right: 35px;
        padding: 12px 0;

        &.active {
          border-bottom: 2px solid #fff;
        }

        a.nuxt-link-exact-active {
          border-bottom: 2px solid #fff;
        }
      }

      .destination {
        margin-top: 35px;
      }
    }
  }

  @media screen and (max-width: 800px) {
    background-image: url(../assets/destination/background-destination-tablet.jpg);
    padding: 0;

    &-container {
      padding: 0 24px;
    }
    &-content {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      width: 100%;
      margin: 0;
      padding: 0;

      &-text {
        .planet {
          display: flex;
          justify-content: center;
          align-items: center;
          margin: 32px 0 26px 0;

          .planet-image {
            width: 170px;
            height: 170px;
          }
        }

        .page-title {
          font-size: 16px;
          line-height: 19px;
        }
      }

      &-explore {
        margin: 0;
        .tabs {
          width: 80%;
          margin: auto;
          display: flex;
          justify-content: space-between;
        }

        .tab-item {
          text-align: center;
          padding: 0;
          margin: 0;
        }

        .destination {
          margin-top: 20px;
          text-align: center;
        }
      }
    }
  }
}
</style>
