<template>
  <div class="hero">
    <div class="hero-container">
      <div class="hero-content">
        <transition name="image" mode="out-in">
            <crew :crew="crews[activeTab]" />
        </transition>
        <div class="btn-container">
          <button
            v-for="tab in tabs"
            :key="tab"
            @click="activeTab = tab"
            :class="['btn', activeTab === tab ? 'active' : '']"
          >
            <span>{{ tab }}}</span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import img1 from '../assets/crew/image-douglas-hurley.png'
import img2 from '../assets/crew/image-mark-shuttleworth.png'
import img3 from '../assets/crew/image-victor-glover.png'
import img4 from '../assets/crew/image-anousheh-ansari.png'
export default {
  name: 'crews',
  data: () => ({
    tabs: ['0', '1', '2', '3'],
    activeTab: '0',
    crews: [
      {
        title: 'COMMANDER',
        name: 'DOUGLAS HURLEY',
        description:
          'Douglas Gerald Hurley is an American engineer, former Marine Corps pilot and former NASA astronaut. He launched into space for the third time as commander of Crew Dragon Demo-2.',
        image: img1,
      },
      {
        title: 'mission specialist',
        name: 'mark shuttleworth',
        description:
          'Mark Richard Shuttleworth is the founder and CEO of Canonical, the company behind the Linux-based Ubuntu operating system. Shuttleworth became the first South African to travel to space as a space tourist.',
        image: img2,
      },
      {
        title: 'PILOT',
        name: 'Victor Glover',
        description:
          'Pilot on the first operational flight of the SpaceX Crew Dragon to the International Space Station. Glover is a commander in the U.S. Navy where he pilots an F/A-18.He was a crew member of Expedition 64, and served as a station systems flight engineer. ',
        image: img3,
      },
      {
        title: 'Flight Engineer',
        name: 'Anousheh Ansari',
        description:
          'Anousheh Ansari is an Iranian American engineer and co-founder of Prodea Systems. Ansari was the fourth self-funded space tourist, the first self-funded woman to fly to the ISS, and the first Iranian in space. ',
        image: img4,
      },
    ],
  }),
  computed: {
    Crews() {
      return this.crews.filter((i) => i.image === this.activeTab)
    },
  },
}
</script>

<style lang="scss" scoped>
.hero {
  background-image: url(../assets/crew/background-crew-desktop.jpg);
  height: 900px;
  padding-top: 40px;
  color: #fff;
  &-container {
    padding-left: 55px;
    display: flex;
    height: 100%;
    justify-content: flex-end;
    align-items: flex-end;
  }
  &-content {
    width: 85%;
    margin: 75px auto 0;
    position: relative;
    z-index: 0;
    &-text {
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
          margin-right: 24px;
        }
      }
    }
  }
  .btn-container {
    position: absolute;
    bottom: 100px;
    .btn {
      width: 15px;
      height: 15px;
      background: #ffffff;
      border-radius: 50%;
      border: none;
      opacity: 0.17;
      margin-right: 24px;
      &.active {
        opacity: 1;
      }
      span {
        opacity: 0;
      }
    }
  }
  @media screen and (max-width: 768px) {
    background-image: url(../assets/crew/background-crew-mobile.jpg);
    background-size: cover;
    background-repeat: no-repeat;
    padding: 0;
    height: 100vh;
    &-container {
      padding: 0 24px;
      align-items: flex-start;
    }
    &-content {
      width: 100%;
      margin: 85px 0 0 0;
    }
    .btn-container {
      bottom: 220px;
      left: 130px;
      .btn {
        width: 10px;
        height: 10px;
        margin-right: 16px;
      }
    }
  }
}
</style>

