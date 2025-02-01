<template>
  <section class="gallery-section" id="gallery">
    <h2 class="section-title">Gallery</h2>
    <div class="section-content">
      <ul class="gallery-list">
        <li class="gallery-item" v-for="image in gallery" :key="image.img">
          <img class="gallery-image" :src="image.img" alt="">
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      gallery: [
        {
          img: require("../assets/gallery-1.jpg"),
        },
        {
          img: require("../assets/gallery-2.jpg"),
        },
        {
          img: require("../assets/gallery-3.jpg"),
        },
        {
          img: require("../assets/gallery-4.jpg"),
        },
        {
          img: require("../assets/gallery-5.jpg"),
        },
        {
          img: require("../assets/gallery-6.jpg"),
        }
      ]
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

section {
  padding: 50px 0 100px;

  .gallery-list {
    display: flex;
    flex-wrap: wrap;
    gap: 32px;

    @media (max-width: 900px) {
      gap: 30px;
    }

    .gallery-item {
      width: calc(100% / 3 - 32px);
      border-radius: $border-radius-s;
      overflow: hidden;

      @media (max-width: 900px) {
        width: calc(100% / 2 - 30px);
      }
      @media (max-width: 640px) {
        width: 100%;
      }

      &:hover .gallery-image {
        transform: scale(1.3);
      }

      .gallery-image {
        cursor: zoom-in;
        width: 100%;
        height: 100%;
        transition: 0.3s ease;
      }
    }
  }
}
</style>