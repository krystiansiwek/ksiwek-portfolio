<template>
  <nav class="navigation">
    <g-link
      v-for="(item, index) in items"
      class="navigation__item"
      :class="{ 'navigation__item--active': $route.path == item.link }"
      :to="item.link"
      :key="`${index}-${item.text}`"
    >
      {{ item.text }}
    </g-link>
  </nav>
</template>

<script>
export default {
  name: "Navbar",
  props: {
    items: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>
.navigation {
  text-align: center;

  &__item {
    font-weight: lighter;
    font-size: 2.25rem;
    text-decoration: none;
    color: #ffffff;

    &--active {
      text-decoration: underline;
    }

    &:not(:first-child) {
      &::before {
        content: "|";
        padding: 20px;
        display: inline-block;
      }
    }
  }
}
</style>
