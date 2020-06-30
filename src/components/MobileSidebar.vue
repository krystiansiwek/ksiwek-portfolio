<template>
  <div>
    <nav class="mobile-sidebar" :class="{ 'mobile-sidebar--active': visible }">
      <div
        class="mobile-sidebar__item"
        v-for="(item, index) in items"
        :key="`${index}-${item.text}`"
      >
        <g-link class="mobile-sidebar__item--link" :to="item.link">
          {{ item.text }}
        </g-link>
        <div class="mobile-sidebar__separator"></div>
      </div>
    </nav>
  </div>
</template>

<script>
import Hamburger from "@/components/Hamburger";

export default {
  name: "MobileSidebar",
  components: {
    Hamburger,
  },
  props: {
    visible: {
      type: Boolean,
      required: true,
    },
    items: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>
.mobile-sidebar {
  width: calc(100vw - 60px);
  height: 100vh;
  background: linear-gradient(
      335.9deg,
      #41b883 -66.14%,
      rgba(255, 255, 255, 0) 100%
    ),
    #34495e;
  box-shadow: 2px 2px 8px rgba(0, 0, 0, 0.25);
  position: absolute;
  top: 0;
  left: 0;
  transform: translateX(calc(-100vw - 60px));

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  transition: transform 0.3s 0.1s ease-in-out;
}

.mobile-sidebar__item {
  font-size: calc(2rem + 2vw);

  @media (min-width: 414px) {
    font-size: 2.5rem;
  }

  padding-bottom: 10px;
  font-weight: lighter;
  width: 100%;
  text-align: center;

  &:not(:first-child) {
    margin-top: 90px;
  }

  &--link {
    text-decoration: none;
    color: #ffffff;
  }
}

.mobile-sidebar--active {
  transform: translateX(0px);
}

.mobile-sidebar__separator {
  border-top: 2px solid #ffffff;
  width: 70%;
  margin: 10px auto;
  mix-blend-mode: soft-light;
}
</style>
