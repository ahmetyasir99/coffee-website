<template>
  <section class="testimonials-section" id="testimonials">
    <h2 class="section-title">Testimonials</h2>
    <div class="section-content">
      <div class="slider-content">
        <div class="slider-wrapper">
          <ul class="testimonials-list">
            <Swiper
              slides-per-view="3"
              grab-cursor="true"
              :pagination="{
                clickable: true,
                dynamicBullets: true
              }"
              :modules="modules"
              :navigation="true"
              :breakpoints="{
                0: {
                  slidesPerView: 1
                },
                768: {
                  slidesPerView: 2
                },
                1024: {
                  slidesPerView: 3
                }
              }"
            >
              <swiper-slide v-for="test in testimonials" :key="test.img">
                <li class="testimonial">
                  <img class="user-image" :src="test.img" alt="User" />
                  <h3 class="name">{{ test.name }}</h3>
                  <i class="feedback"
                    >Lorem ipsum dolor sit amet consectetur adipisicing elit.
                    Voluptate, libero!</i
                  >
                </li>
              </swiper-slide>
            </Swiper>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";
import { Navigation, Pagination } from "swiper/modules";

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  data() {
    return {
      modules: [Navigation, Pagination],
      testimonials: [
        {
          img: require("../assets/user-1.jpg"),
          name: "Sarah Johnson",
        },
        {
          img: require("../assets/user-2.jpg"),
          name: "Glenn Rhee",
        },
        {
          img: require("../assets/user-3.jpg"),
          name: "Shane Walsh",
        },
        {
          img: require("../assets/user-4.jpg"),
          name: "Lori Grimes",
        },
        {
          img: require("../assets/user-5.jpg"),
          name: "Daryl Dixon",
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
  padding: 50px 0 100px;
  background: $light-pink-color;

  .slider-wrapper {
    overflow: hidden;
    margin: 0 60px 50px;

    @media (max-width: 640px) {
      margin: 0 0 30px;
    }
  }

  .testimonial {
    display: flex;
    padding: 35px;
    text-align: center;
    flex-direction: column;
    align-items: center;
    user-select: none;

    .user-image {
      width: 180px;
      height: 180px;
      object-fit: cover;
      margin-bottom: 50px;
      border-radius: $border-radius-circle;
    }

    .name {
      margin-bottom: 16px;
      font-size: $font-size-m;
    }

    .feedback {
      line-height: 25px;
    }
  }
}
</style>

<style>
.swiper-pagination-bullet {
  width: 15px;
  height: 15px;
  opacity: 1;
  background: #f3961c;
}

.swiper-button-prev, .swiper-button-next {
  color: #f3961c;
}

@media screen and (max-width: 640px) {
  .swiper-button-prev, .swiper-button-next {
    display: none;
  }
}
</style>