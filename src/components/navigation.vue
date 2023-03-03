<template>
  <header class="header">
    <div class="container">
      <a href="#" class="logo">
        <span>LOGO</span>
      </a>
      <nav class="navigation">
        <ul class="navigation__list">
          <li
            class="navigation__item"
            v-for="(link, index) in links"
            :key="index"
          >
            <a href="link.url" class="navigation__link">{{ link.label }}</a>
          </li>
        </ul>
        <div class="navigation__buttons">
          <linkBtn class="navigation__button">Kontakt</linkBtn>
          <button class="navigation__button">Podporte nás</button>
        </div>
      </nav>
    </div>
  </header>
</template>
<script>
import linkButton from "./linkBtn.vue";

export default {
  name: "headerNav",
  components: {
    linkButton,
  },
  data() {
    return {
      links: [
        {
          label: "Domov",
          url: "#",
        },
        {
          label: "O nás",
          url: "#",
        },
        {
          label: "Aktivity",
          url: "#",
        },
        {
          label: "Legality",
          url: "#",
        },
      ],
    };
  },
};
</script>
<style lang="scss" scoped>
@use "../assets/styles/abstracts.scss" as *;

.header {
  box-shadow: 0 0 2.4rem rgba($black, 0.1);
  height: 8rem;
  display: flex;
  align-items: center;
  justify-content: stretch;

  .container {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .navigation {
    font-size: 1.8rem;
    display: flex;
    gap: 4rem;
    align-items: center;

    &__list {
      display: flex;
      gap: 4rem;
    }

    &__item {
    }
    &__link {
      &:link,
      &:visited {
        color: $color--text-dark;
        transition: $animation--time-short;
      }
      &:hover {
        color: $green-tint;
      }
    }
    &__buttons {
      display: flex;
      gap: 4rem;
    }
  }
}
</style>
