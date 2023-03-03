<template>
  <component
    :is="isLink ? 'a' : 'button'"
    :class="[type, size, fullLength]"
    :href="isLink ? href : null"
    class="btn"
  >
    <slot></slot>
  </component>
</template>

<script>
export default {
  name: "LinkBtn",
  props: {
    isLink: Boolean,
    type: {
      type: String,
      default: "default",
    },
    size: {
      type: String,
      default: "medium",
    },
    fullLength: {
      type: String,
      default: "",
    },
    href: {
      type: String,
      default: "#",
    },
  },
};
</script>

<style lang="scss" scoped>
@use "../assets/styles/abstracts.scss" as *;

.btn {
  display: inline-block;

  border-radius: 6px;

  text-decoration: none;
  color: $color--text-light;

  transition: $animation--time-short;

  cursor: pointer;

  &:active {
    box-shadow: 0 0 0 0.5rem rgba($color--primary-btn-background-hover, 0.4);
  }
}

.primary {
  background-color: $color--primary-btn-background;
  border: 2px solid $color--primary-btn-background;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;

  &:hover {
    background-color: $color--primary-btn-background-hover;
    border: 2px solid $color--primary-btn-background-hover;
  }
}

.secondary {
  background-color: transparent;
  border: 2px solid $color--primary-btn-background;
  color: $color--primary-btn-background;
  &:hover {
    background-color: $color--primary-btn-background;
    border: 2px solid $color--primary-btn-background;
    color: $color--text-light;
  }
}

.tertiary {
  background-color: transparent;
  border: none;
  color: $color--primary-btn-background;
  &:hover {
    text-decoration: underline;
  }
}
.small {
  padding: 0.8rem 2.8rem;
  font-size: 1.6rem;
}
.medium {
  padding: 1rem 3.6rem;
  font-size: 2rem;
}
.large {
  padding: 1.2rem 4.2rem;
  font-size: 2.2rem;
}
.full-length {
  width: 100%;
}
</style>
