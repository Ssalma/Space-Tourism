<template>
  <nav>
    <img src="@/assets/shared/logo.svg" class="logo" alt="" />
    <label for="hamburger" class="ham-label">
      <img src="../assets/shared/icon-hamburger.svg" alt="" />
    </label>
    <input type="checkbox" name="ham" id="hamburger" />
    <ul class="nav-content">
      <label for="hamburger" class="close-ham-label">
        <img src="../assets/shared/icon-close.svg" alt="" class="close" />
      </label>
      <div class="link-wrapper">
        <li>
          <NuxtLink
            class="nav-link"
            to="/"
            style="text-decoration: none; color: inherit"
          >
            <span>{{ value.home }}</span>
            HOME
          </NuxtLink>
        </li>
        <li>
          <NuxtLink
            class="nav-link"
            to="/destination"
            style="text-decoration: none; color: inherit"
          >
            <span>{{ value.destination }}</span>
            DESTINATION
          </NuxtLink>
        </li>
        <li>
          <NuxtLink
            class="nav-link"
            to="/crew"
            style="text-decoration: none; color: inherit"
          >
            <span>{{ value.crew }}</span>
            CREW
          </NuxtLink>
        </li>
        <li>
          <NuxtLink
            class="nav-link"
            to="/technology"
            style="text-decoration: none; color: inherit"
          >
            <span>{{ value.technology }}</span>
            TECHNOLOGY
          </NuxtLink>
        </li>
      </div>
    </ul>
  </nav>
</template>

<script>
export default {
  props: {},
  data: () => ({
    value: {
      home: '00',
      destination: ' 01',
      crew: '02',
      technology: '03',
    },
  }),
}
</script>

<style lang="scss" scoped>
nav {
  width: 100%;
  height: 100px;
  position: fixed;
  top: 0;
  right: 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: #fff;
  z-index: 100;
  padding-left: 55px;
  .ham-label {
    display: none;
  }
  .close-ham-label{
    display: none;
  }
  #hamburger {
    display: none;
  }
  .logo {
    width: 48px;
    height: 48px;
  }
  li {
    list-style-type: none;
  }
  .link-wrapper{
    display: flex;
  }
  a.nuxt-link-exact-active {
    border-bottom: 2px solid #fff;
  }
  .nav-content {
    z-index: 100;
    height: 96px;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
    padding-left: 123px;
    background: rgba(255, 255, 255, 0.04);
    backdrop-filter: blur(81.5485px);
    padding-right: 115px;
    &::before {
      content: '';
      width: 470px;
      border: 1px solid #fff;
      position: absolute;
      left: -450px;
      transition: cubic-bezier(0.075, 0.82, 0.165, 1);
      opacity: 0.25;
    }
  }
  .nav-link {
    font-family: 'Barlow Condensed';
    font-weight: 300;
    font-size: 16px;
    line-height: 19px;
    letter-spacing: 2.7px;
    list-style-type: none;
    margin-right: 48px;
    cursor: pointer;
    height: 95px;
    display: flex;
    align-items: center;
    text-decoration: none;
    &:hover {
      border-bottom: 2px solid #fff;
    }
    span {
      font-weight: 600;
      margin-right: 10px;
    }
  }
}
@media screen and (max-width: 768px) {
  nav {
    justify-content: space-between;
    padding: 0 24px;
    .nav-link {
      height: 40px;
      margin-bottom: 34px;
    }
    .nav-content {
      position: absolute;
      padding: 34px;
      right: -100vw;
      justify-content: flex-start;
      align-items: flex-start;
      transition: 150ms ease-out;

      &::before {
        display: none;
      }
    }
    .link-wrapper{
      margin-top: 100px;
      display: block;
    }
    .logo {
      width: 40px;
      height: 40px;
    }
    a.nuxt-link-exact-active {
      border-bottom:none;
      font-weight: 500;
    }
    .ham-label {
      display: flex;
    }
    .close-ham-label{
      display: flex;
      
    }
    .close {
      width: 19px;
      height: 19px;
    }
    #hamburger {
      display: none;
    }
    #hamburger:checked ~ .nav-content {
      width: 255px;
      height: 100vh;
      position: absolute;
      top: -18px;
      right: -24px;
    }
  }
}
</style>