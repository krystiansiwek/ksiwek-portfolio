<template>
  <button
    class="hamburger"
    :class="{ 'hamburger--active': isActive }"
    @click="$emit('click')"
  >
    <span class="hamburger__box">
      <span class="hamburger__inner"></span>
    </span>
  </button>
</template>

<script>
export default {
  name: "Hamburger",
  props: {
    isActive: {
      type: Boolean,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>
@mixin hamburger-line {
  width: 100%;
  height: 4px;
  background-color: #ffffff;
  position: absolute;
}

.hamburger {
  padding: 10px;
  display: inline-block;
  cursor: pointer;
  background-color: transparent;
  border: 0;
  margin: 0;
}

.hamburger__box {
  width: 40px;
  height: 20px;
  display: inline-block;
  position: relative;
}

.hamburger__inner {
  @include hamburger-line;

  left: 0;
  top: 50%;
  transform: translateY(-50%);
  transition: background-color 0.3s 0.1s ease-in-out;
}

.hamburger__inner::before,
.hamburger__inner::after {
  @include hamburger-line;

  content: "";
  left: 0;
  transition: transform 0.3s ease-in-out;
}

.hamburger__inner::before {
  top: -10px;
}

.hamburger__inner::after {
  top: 10px;
}

.hamburger--active .hamburger__inner {
  background-color: transparent;
}

.hamburger--active .hamburger__inner::before {
  transform: translateY(10px) rotate(45deg);
}

.hamburger--active .hamburger__inner::after {
  transform: translateY(-10px) rotate(-45deg);
}
</style>
