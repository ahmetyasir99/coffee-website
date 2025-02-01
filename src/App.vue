<template>
  <the-header></the-header>
  <main>
    <hero-section></hero-section>
    <about-section></about-section>
    <menu-section></menu-section>
    <testimonials-section></testimonials-section>
    <gallery-section></gallery-section>
    <contact-section></contact-section>
    <footer-section></footer-section>
  </main>
</template>

<script>
import AboutSection from './components/AboutSection.vue';
import HeroSection from './components/HeroSection.vue';
import TheHeader from './components/TheHeader.vue';
import MenuSection from './components/MenuSection.vue';
import TestimonialsSection from './components/TestimonialsSection.vue';
import GallerySection from './components/GallerySection.vue';
import ContactSection from './components/ContactSection.vue';
import FooterSection from './components/FooterSection.vue';

export default {
  components: {
    TheHeader,
    HeroSection,
    AboutSection,
    MenuSection,
    TestimonialsSection,
    GallerySection,
    ContactSection,
    FooterSection
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Lobster&family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Lobster&family=Miniver&family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

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

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Poppins", sans-serif;
}

html {
  scroll-behavior: smooth;
}

ul {
  list-style: none;
}

a {
  text-decoration: none;
}

button {
  cursor: pointer;
  border: none;
  background: none;
}

img {
  width: 100%;
}

.section-content {
  margin: 0 auto;
  padding: 0 20px;
  max-width: $site-max-width;
}

.section-title {
  text-align: center;
  padding: 60px 0 100px;
  text-transform: uppercase;
  font-size: $font-size-xl;

  &::after {
    content: "";
    width: 80px;
    height: 5px;
    display: block;
    margin: 10px auto 0;
    border-radius: $border-radius-s;
    background: $secondary-color;
  }
}
</style>