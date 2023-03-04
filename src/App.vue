<script setup>
import linkButton from "./components/linkBtn.vue";
import headerNav from "./components/navigation.vue";
import heroSection from "./components/hero.vue";
</script>

<template>
  <headerNav></headerNav>
  <heroSection></heroSection>
  <div class="container buttons">
    <linkButton type="primary" href="#"> Primary </linkButton>
    <linkButton isLink type="secondary" href="#"> Secondary </linkButton>
    <linkButton type="tertiary" href="#"> Tertiary </linkButton>
  </div>
</template>

<style lang="scss">
//general and reusable styles
@import "./assets/styles/reset.scss";
@import "./assets/styles/abstracts.scss";

h1 {
  color: $white;
  font-size: 8rem;
  line-height: 1.3;
  width: 60%;
  margin-bottom: 3.6rem;
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
</style>
