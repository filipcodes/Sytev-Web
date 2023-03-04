<script setup>
import linkBtn from "./components/linkBtn.vue";
import headerNav from "./components/navigation.vue";
</script>

<template>
  <headerNav></headerNav>
  <div class="container buttons">
    <linkBtn type="primary" href="#"> Primary </linkBtn>
    <linkBtn isLink="true" type="secondary" href="#"> Secondary </linkBtn>
    <linkBtn type="tertiary" href="#"> Tertiary </linkBtn>
  </div>
</template>

<style lang="scss">
//general and reusable styles
@import "assets/styles/reset";
@import "assets/styles/abstracts";

.container {
  max-width: 120rem;
  margin: 0 auto;
  padding: 0 2.4rem;
}

.buttons {
  padding-top: 2rem;

  @include center-content;
  gap: 5rem;
}
</style>
