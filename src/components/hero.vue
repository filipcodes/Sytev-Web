<template>
  <section class="hero">
    <div class="container">
      <span class="uptitle">Dobrovoľníctvo</span>
      <h1 class="hero__title">Konaj dobro a pomôž svojmu okoliu</h1>
      <linkButton type="primary" isLink href="#">Zisti viac</linkButton>
    </div>
  </section>
  <swiper
    :modules="modules"
    :slides-per-view="3"
    navigation
    :pagination="{ clickable: true }"
    @swiper="onSwiper"
    @slideChange="onSlideChange"
  >
    <swiper-slide>Slide 1</swiper-slide>
    <swiper-slide>Slide 2</swiper-slide>
    <swiper-slide>Slide 3</swiper-slide>
    <swiper-slide>Slide 4</swiper-slide>
    <swiper-slide>Slide 5</swiper-slide>
    <swiper-slide>Slide 6</swiper-slide>
  </swiper>
</template>
<script>
import { Navigation, Pagination } from "swiper";

import { Swiper, SwiperSlide } from "swiper/vue";
//I also want modules: Navigation, Pagination ?, autoplay, disable mouse
import linkButton from "./linkBtn.vue";

import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";

export default {
  name: "heroSection",
  components: {
    linkButton,
    Swiper,
    SwiperSlide,
  },
  setup() {
    const onSwiper = (swiper) => {
      console.log(swiper);
    };
    const onSlideChange = () => {
      console.log("slide change");
    };
    return {
      onSwiper,
      onSlideChange,
      modules: [Navigation, Pagination],
    };
  },
};
</script>
<style lang="scss" scoped>
@use "../assets/styles/abstracts.scss" as *;
.hero {
  padding-top: 10rem;
  height: 100vh;
  background: linear-gradient(to bottom, rgba($black, 0.6), rgba($black, 0.6)),
    url("../assets/images/interior_test.jpg");
  background-size: cover;

  @include center-content;
}
</style>
