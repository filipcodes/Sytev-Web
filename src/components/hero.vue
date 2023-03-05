<template>
  <section class="hero">
    <swiper
      class="swiper__element"
      :modules="modules"
      :slides-per-view="1"
      navigation
      :loop="true"
      :autoplay="{ delay: 5000 }"
      :pagination="{ clickable: true }"
      @swiper="onSwiper"
      @slideChange="onSlideChange"
    >
      <swiper-slide class="swiper__slide">
        <div class="container">
          <span class="uptitle">Dobrovoľníctvo</span>
          <h1 class="hero__title">Konaj dobro a pomôž svojmu okoliu</h1>
          <p class="hero__subtitle">
            V našom programe dobrovoľníctva je už viac ako 5000 študentov. Práve
            TY sa môžeš stať jedným z nich!
          </p>
          <linkButton type="primary" isLink href="#">Zisti viac</linkButton>
        </div>
      </swiper-slide>
      <swiper-slide class="swiper__slide">
        <div class="container">
          <span class="uptitle">Show your talent</span>
          <h1 class="hero__title">Objav svoj talent</h1>
          <p class="hero__subtitle">
            V našom programe dobrovoľníctva je už viac ako 5000 študentov. Práve
            TY sa môžeš stať jedným z nich!
          </p>
          <linkButton type="primary" isLink href="#">Zisti viac</linkButton>
        </div>
      </swiper-slide>
      <swiper-slide class="swiper__slide">
        <div class="container">
          <span class="uptitle">Klubovňa</span>
          <h1 class="hero__title">Využi čas naplno</h1>
          <linkButton type="primary" isLink href="#">Zisti viac</linkButton>
        </div>
      </swiper-slide>
    </swiper>
  </section>
</template>

<script>
import { Autoplay, Navigation, Pagination } from "swiper";

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
      modules: [Navigation, Pagination, Autoplay],
    };
  },
};
</script>
<style lang="scss" scoped>
@use "../assets/styles/abstracts.scss" as *;
.hero {
  padding-top: 10rem;
  height: calc(100vh - 10rem);
  background: linear-gradient(to bottom, rgba($black, 0.6), rgba($black, 0.6)),
    url("../assets/images/interior_test.jpg");
  background-size: cover;

  margin-bottom: 12rem;

  @include center-content;

  .container {
    width: 140rem;
  }

  &__subtitle {
    font-size: 1.8rem;
    color: $color--text-light;
    width: 40%;
    margin-bottom: 4.8rem;
  }
}

.swiper__element {
  background-color: $black;
}

.swiper__slide {
  padding-top: 10rem;
  height: 100vh;
  background: linear-gradient(to bottom, rgba($black, 0.6), rgba($black, 0.6)),
    url("../assets/images/interior_test.jpg");
  background-size: cover;

  @include center-content;
}

.swiper-button-next {
  color: $green !important;
}
</style>
