<template>
  <header class="header">
    <div class="container">
      <a href="#" class="logo">
        <img src="../assets/images/sytev_logo.png" alt="Logo of Systev" />
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
      </nav>
      <div class="navigation__buttons">
        <linkButton
          isLink
          type="secondary"
          size="small"
          class="navigation__button"
          >Kontakt</linkButton
        >
        <linkButton
          isLink
          type="primary"
          size="small"
          class="navigation__button"
        >
          Podporte nás
        </linkButton>
      </div>
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
@use "../assets/styles/abstracts" as *;

.header {
  box-shadow: 0 0 2.4rem rgba($black, 0.1);
  height: 8.6rem;
  display: flex;
  align-items: center;
  justify-content: stretch;
  position: fixed;
  width: 100%;
  z-index: 100;
  background-color: $white;

  .container {
    width: 100%;
    max-width: 160rem;
    display: flex;
    align-items: center;
  }

  .logo {
    margin-right: 5.6rem;
    img {
      height: 6.4rem;
    }
  }

  .navigation {
    font-size: 1.8rem;
    font-weight: 400;
    letter-spacing: 1px;

    margin-right: auto;
    &__list {
      display: flex;
      gap: 4.2rem;
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
      gap: 1.6rem;
    }
  }
}
</style>
