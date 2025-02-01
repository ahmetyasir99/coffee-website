<template>
  <header>
    <nav class="navbar section-content">
      <router-link class="logo" :to="{name: 'Home'}"><h2 class="logo-text">☕ Coffee</h2></router-link>
      <ul :class="{'opened-menu': open}" class="nav-menu">
        <button v-show="open" @click="toggleMenu" id="menu-close-button">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 384 512"><path d="M342.6 150.6c12.5-12.5 12.5-32.8 0-45.3s-32.8-12.5-45.3 0L192 210.7 86.6 105.4c-12.5-12.5-32.8-12.5-45.3 0s-12.5 32.8 0 45.3L146.7 256 41.4 361.4c-12.5 12.5-12.5 32.8 0 45.3s32.8 12.5 45.3 0L192 301.3 297.4 406.6c12.5 12.5 32.8 12.5 45.3 0s12.5-32.8 0-45.3L237.3 256 342.6 150.6z"/></svg>
        </button>
        <li v-for="nav in navItems" :key="nav.name">
          <router-link @click="toggleMenu" class="link" :to="nav.href">{{ nav.name }}</router-link>
        </li>
      </ul>
      <button @click="toggleMenu" id="menu-open-button">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="M0 96C0 78.3 14.3 64 32 64l384 0c17.7 0 32 14.3 32 32s-14.3 32-32 32L32 128C14.3 128 0 113.7 0 96zM0 256c0-17.7 14.3-32 32-32l384 0c17.7 0 32 14.3 32 32s-14.3 32-32 32L32 288c-17.7 0-32-14.3-32-32zM448 416c0 17.7-14.3 32-32 32L32 448c-17.7 0-32-14.3-32-32s14.3-32 32-32l384 0c17.7 0 32 14.3 32 32z"/></svg>
      </button>
      <div v-show="open" :class="{'blur-effect': open}"></div>
    </nav>
  </header>
</template>

<script>
export default {
  components: {

  },
  data() {
    return {
      open: false,
      navItems: [
        {
          name: 'Home',
          href: {name: 'Home',  hash: 'main'}
        },
        {
          name: 'About',
          href: {name: 'About', hash: '#about'}
        },
        {
          name: 'Menu',
          href: {name: 'Menu',  hash: '#menu'}
        },
        {
          name: 'Testimonials',
          href: {name: 'Testimonials',  hash: '#testimonials'}
        },
        {
          name: 'Gallery',
          href: {name: 'Gallery',  hash: '#gallery'}
        },
        {
          name: 'Contact',
          href: {name: 'Contact',  hash: '#contact'}
        }
      ]
    }
  },
  methods: {
    toggleMenu() {
        this.open = !this.open;
    }
  }
}
</script>

<style lang="scss" scoped>
/*variables*/
$white-color: #ffffff;
$dark-color: #252525;
$primary-color: #3b141c;
$secondary-color: #f3961c;
$light-pink-color: #faf4f5;
$medium-gray-color: #ccc;

$font-size-s: 0.9rem;
$font-size-n: 1rem;
$font-size-m: 1.12rem;
$font-size-l: 1.5rem;
$font-size-xl: 2rem;
$font-size-xxl: 2.3rem;

$font-weight-normal: 400;
$font-weight-medium: 500;
$font-weight-semibold: 600;
$font-weight-bold: 700;

$border-radius-s: 8px;
$border-radius-m: 30px;
$border-radius-circle: 50%;

$site-max-width: 1300px;
/*variables end*/
header {
  background: $primary-color;
  position: fixed;
  width: 100%;
  z-index: 5;
  background: $primary-color;
}

.blur-effect {
  position: fixed;
  left: 0;
  top: 0;
  height: 100%;
  width: 100%;
  backdrop-filter: blur(5px);
  background: rgba(0, 0, 0, 0.2);
  z-index: 4;
}

nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 20px;

  #menu-open-button {
    display: block;

    @media (min-width: 900px) {
      display: none;
    }

    svg {
      width: 20px;
      height: 20px;
      filter: invert(1);
    }
  }

  ul {
    display: flex;
    gap: 10px;

    #menu-close-button {
      position: absolute;
      right: 30px;
      top: 30px;

      svg {
        width: 15px;
        height: 15px;
      }
    }

    @media (max-width: 900px) {
      position: fixed;
      left: -300px;
      top: 0;
      width: 300px;
      height: 100%;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding-top: 100px;
      background: $white-color;
      transition: left 0.2s ease;
      z-index: 5;

      &.opened-menu {
        left: 0;
      }
    }

    .link {
      padding: 10px 18px;
      font-size: $font-size-m;
      color: $white-color;
      border-radius: $border-radius-m;
      transition: 0.3s ease;

      &:hover {
        color: $primary-color;
        background: $secondary-color;
      }

      @media (max-width: 900px) {
        color: $dark-color;
        display: block;
        margin-top: 17px;
        font-size: $font-size-l;
      }
    }
  }
}

.logo {
  color: $white-color;
  font-size: $font-size-l;
  font-weight: $font-weight-semibold;

  h2 {
    white-space: nowrap;
  }
}
</style>