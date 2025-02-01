<template>
  <section class="hero-section">
    <div class="section-content">
      <div class="hero-details">
        <h2 class="title">Best Coffee</h2>
        <h3 class="subtitle">Make your day great with our special coffies!</h3>
        <p class="description">
          Welcome to our coffee paradise, where every bean tells a story and
          every cup sparks joy.
        </p>
        <div class="buttons">
          <router-link to="#" class="button order-now">Order Now</router-link>
          <router-link to="#" class="button contact-us">Contact Us</router-link>
        </div>
      </div>
      <div class="hero-image-wrapper">
        <img
          class="hero-image"
          src="../assets/coffee-hero-section.png"
          alt=""
        />
      </div>
    </div>
  </section>
</template>

<script>
export default {};
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
  background: $primary-color;
  min-height: 100vh;
}

.section-content {
  display: flex;
  align-items: center;
  min-height: 100vh;
  color: $white-color;
  justify-content: space-between;

  @media (max-width: 900px) {
      gap: 50px;
      text-align: center;
      padding: 30px 20px 20px;
      flex-direction: column-reverse;
      justify-content: center;
    }

  .title {
    font-size: $font-size-xxl;
    color: $secondary-color;
    font-family: "Miniver", sans-serif;
  }

  .subtitle {
    margin-top: 8px;
    max-width: 70%;
    font-size: $font-size-xl;
    font-weight: $font-weight-semibold;

    @media (max-width: 900px) {
      max-width: 100%;
    }
  }

  .description {
    font-size: $font-size-m;
    max-width: 70%;
    margin: 24px 0 40px;

    @media (max-width: 900px) {
      max-width: 100%;
    }
  }

  .buttons {
    display: flex;
    gap: 12px;

    @media (max-width: 900px) {
      justify-content: center;
    }

    .button {
      padding: 10px 26px;
      color: $primary-color;
      background: $secondary-color;
      border-radius: $border-radius-m;
      font-weight: $font-weight-medium;
      border: 2px solid transparent;
      transition: 0.3s ease;

      &:hover {
        color: $white-color;
        border-color: $white-color;
        background: transparent;
      }

      &.contact-us {
        color: $white-color;
        border-color: $white-color;
        background: transparent;

        &:hover {
          color: $primary-color;
          border-color: transparent;
          background: $secondary-color;
        }
      }
    }
  }

  .hero-image-wrapper {
    max-width: 500px;
    margin-right: 36px;

    @media (max-width: 900px) {
      max-width: 270px;
      margin-right: 0;
    }
  }
}
</style>