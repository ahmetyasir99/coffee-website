<template>
  <section class="menu-section" id="menu">
    <h2 class="section-title">Our Menu</h2>
    <div class="section-content">
      <ul class="menu-list">
        <li class="menu-item" v-for="item in menu" :key="item.img">
          <img class="menu-image" :src="item.img" alt="" />
          <h3 class="name">Lorem, ipsum dolor.</h3>
          <p class="text">
            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Doloribus,
            ducimus.
          </p>
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      menu: [
        {
          img: require("../assets/hot-beverages.png"),
        },
        {
          img: require("../assets/cold-beverages.png"),
        },
        {
          img: require("../assets/refreshment.png"),
        },
        {
          img: require("../assets/special-combo.png"),
        },
        {
          img: require("../assets/desserts.png"),
        },
        {
          img: require("../assets/burger-frenchfries.png"),
        },
      ],
    };
  },
};
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
section {
  background: $dark-color;
  color: $white-color;
  padding: 50px 0 100px;
}

.menu-list {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: 110px;
  justify-content: space-between;

  @media (max-width: 1024px) {
    gap: 30px;
  }
  @media (max-width: 640px) {
    gap: 60px;
  }

  .menu-item {
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: space-between;
    text-align: center;
    width: calc(100% / 3 - 110px);

    @media (max-width: 1024px) {
      width: calc(100% / 2 - 30px);
    }

    @media (max-width: 640px) {
      width: 100%;
    }

    .menu-image {
      max-width: 83%;
      aspect-ratio: 1;
      margin-bottom: 15px;
      object-fit: contain;

      @media (max-width: 1024px) {
        max-width: 200px;
      }
    }

    .name {
      margin: 12px 0;
      font-size: $font-size-l;
      font-weight: $font-weight-semibold;
    }

    .text {
      font-size: $font-size-m;
    }
  }
}
</style>