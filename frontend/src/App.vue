<script setup>
import linkButton from "./components/linkBtn.vue";
import headerNav from "./components/navigation.vue";
import heroSection from "./components/hero.vue";
import footerSection from "./components/footer.vue";
</script>

<template>
  <headerNav></headerNav>
  <heroSection></heroSection>
  <div class="container buttons">
    <linkButton type="primary" href="#"> Primary </linkButton>
    <linkButton isLink type="secondary" href="#"> Secondary </linkButton>
    <linkButton type="tertiary" href="#"> Tertiary </linkButton>
  </div>
  <footerSection></footerSection>
</template>

<style lang="scss">
//general and reusable styles
@import "assets/styles/reset";
@import "assets/styles/abstracts";

h1 {
  color: $white;
  font-size: 8rem;
  line-height: 1.3;
  margin-bottom: 2rem;
  width: 70%;
  letter-spacing: 1px;
}

.container {
  max-width: 140rem;
  margin: 0 auto;
  padding: 0 2.4rem;
}
.uptitle {
  color: $green-tint;
  font-size: 1.8rem;
  text-transform: uppercase;
  font-weight: 600;
  letter-spacing: 1px;
  background-color: $white;
  display: inline-block;
  padding: 0 1rem;
  margin-bottom: 1.6rem;
  border-radius: $border-radius-small;
}

.buttons {
  padding-top: 2rem;

  @include center-content;
  gap: 5rem;
}

.swiper-button-next,
.swiper-button-prev {
  color: $white;
  width: 10rem;
  height: 10rem;
  &::after {
    font-size: 5.6rem;
  }
}

.swiper-pagination-bullet {
  background-color: rgba($white, 0.7);
}

.swiper-pagination-bullet-active {
  background: $white;
}
</style>
