<template>
  <g-link :to="href">
    <img
      class="icon"
      :src="image"
      :width="width"
      :height="height"
      @mouseover="hover = true"
      @mouseleave="hover = false"
    />
  </g-link>
</template>

<script>
export default {
  name: "Icon",
  props: {
    image: {
      type: String,
      required: true,
    },
    href: {
      type: String,
      default: "#",
    },
    width: {
      type: String,
      default: "100",
    },
    height: {
      type: String,
      default: "100",
    },
  },
  data() {
    return {
      hover: false,
    };
  },
};
</script>

<style lang="scss" scoped>
.icon {
  transition: all 0.1s ease-in-out;
  filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25));
}

.icon:hover {
  transform: scale(1.25);
}
</style>
