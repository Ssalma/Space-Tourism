<template>
  <div class="tech">
    <div class="tech-container">
      <h2 class="page-title"><span>03</span>SPACE LAUNCH 101</h2>
      <div class="tech-content">
        <div class="btn-container">
          <button
            v-for="tab in tabs"
            :key="tab"
            @click="activeTab = tab"
            :class="['btn', activeTab === tab ? 'active' : '']"
          >
            <span class="index">{{ Number(tab) + 1 }}</span>
          </button>
        </div>
        <Techtext class="tech-text" :technology="technology[activeTab]" />
        <Techimage
          class="tech-image"
          :image="image[activeTab]"
          :imageMobile="mobileImage[activeTab]"
        />
      </div>
    </div>
  </div>
</template>

<script>
import launchImg from '../assets/technology/image-launch-vehicle-portrait.jpg'
import spaceportImg from '../assets/technology/image-spaceport-portrait.jpg'
import capsuleImg from '../assets/technology/image-space-capsule-portrait.jpg'
import launchImgMobile from '../assets/technology/image-launch-vehicle-landscape.jpg'
import spaceportImgMobile from '../assets/technology/image-spaceport-landscape.jpg'
import capsuleImgMobile from '../assets/technology/image-space-capsule-landscape.jpg'
export default {
  data: () => ({
    tabs: ['0', '1', '2'],
    activeTab: '0',
    technology: [
      {
        ellipses: 'The terminology…',
        heading: 'Launch vehicle',
        description: `A launch vehicle or carrier rocket is a rocket-propelled vehicle used to carry a payload from Earth's surface to space, usually to Earth orbit or beyond. Our WEB-X carrier rocket is the most powerful in operation. Standing 150 metres tall, it's quite an awe-inspiring sight on the launch pad!`,
      },
      {
        ellipses: 'The terminology…',
        heading: 'spaceport',
        description: `A spaceport or cosmodrome is a site for launching (or receiving) spacecraft, by analogy to the seaport for ships or airport for aircraft. Based in the famous Cape Canaveral, our spaceport is ideally situated to take advantage of the Earth’s rotation for launch.`,
      },
      {
        ellipses: 'The terminology…',
        heading: 'space capsule',
        description: `A space capsule is an often-crewed spacecraft that uses a blunt-body reentry capsule to reenter the Earth's atmosphere without wings. Our capsule is where you'll spend your time during the flight. It includes a space gym, cinema, and plenty of other activities to keep you entertained.`,
      },
    ],
    image: [launchImg, spaceportImg, capsuleImg],
    mobileImage: [launchImgMobile, spaceportImgMobile, capsuleImgMobile],
  }),
  computed: {
    images() {
      return this.image.map((i) => i === this.activeTab)
    },
  },
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
.tech {
  display: flex;
  justify-content: center;
  &-container {
    background-image: url(../assets/technology/background-technology-desktop.jpg);
    height: 900px;
    padding: 200px 0 0 55px;
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
  &-content {
    display: grid;
    grid-template-columns: 1fr 3fr 4fr;
    margin-top: 26px;
    .btn-container {
      display: flex;
      flex-direction: column;
      justify-content: center;
      .btn {
        width: 80px;
        height: 80px;
        border-radius: 50%;
        background: transparent;
        mix-blend-mode: normal;
        opacity: 0.25;
        border: 1px solid #ffffff;
        box-sizing: border-box;
        font-family: Bellefair;
        font-weight: normal;
        font-size: 32px;
        line-height: 37px;
        text-align: center;
        letter-spacing: 2px;
        color: #fff;
        margin-bottom: 30px;
        &.active {
          background: #ffffff;
          opacity: 1;
          color: #0b0d17;
        }
      }
    }
    .tech-text {
      display: flex;
      flex-direction: column;
      justify-content: center;
    }
    .tech-image {
      display: flex;
      justify-content: flex-end;
    }
  }
  @media screen and (max-width: 768px) {
    &-container {
      background-image: url(../assets/technology/background-technology-tablet.jpg);
      height: 100vh;
      padding: 100px 24px 0;

      .page-title {
        text-align: center;
        font-size: 16px;
        line-height: 19px;
        margin-top: 24px;
        span {
          margin-right: 16px;
        }
      }
    }
    &-content {
      grid-template-columns: 1fr;
      .tech-image {
        grid-row: 1;
      }
      .btn-container {
        flex-direction: row;
        margin: 34px 0 26px 0;
        .btn {
          width: 40px;
          height: 40px;
          font-size: 16px;
          line-height: 18px;
          margin-bottom: 0;
          margin-right: 16px;
        }
      }
    }
  }
}
</style>