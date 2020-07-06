<template>
  <Layout>
    <div>
      <Hamburger
        class="mobile-only"
        :isActive="isSidebarActive"
        @click="isSidebarActive = !isSidebarActive"
      ></Hamburger>
      <MobileSidebar :items="items" :visible="isSidebarActive" />
    </div>
    <div class="home">
      <Navbar :items="items" class="desktop-only" />
      <h1 class="home__name">YOU CAN FIND ME ON</h1>
      <div class="tech-icons">
        <icon
          class="tech-icon"
          v-for="icon in icons"
          :key="icon.src"
          :image="icon.src"
          :href="icon.href"
        ></icon>
      </div>
    </div>
  </Layout>
</template>

<script>
import Navbar from "@/components/Navbar";
import MobileSidebar from "@/components/MobileSidebar";
import Hamburger from "@/components/Hamburger";
import Icon from "@/components/Icon";
import github from "@/assets/github.svg";
import twitter from "@/assets/twitter.svg";
import linkedin from "@/assets/linkedin.svg";

export default {
  components: {
    Navbar,
    MobileSidebar,
    Hamburger,
    Icon,
  },
  metaInfo: {
    title: "KSiwek",
  },
  data() {
    return {
      isSidebarActive: false,
      items: [
        {
          text: "home",
          link: "/",
        },
        {
          text: "technologies",
          link: "/technologies",
        },
        {
          text: "contact",
          link: "/contact",
        },
      ],
      icons: [
        {
          src: github,
          href: "https://github.com/krystiansiwek",
        },
        {
          src: twitter,
          href: "https://twitter.com/_ksiwek",
        },
        {
          src: linkedin,
          href: "#",
        },
      ],
    };
  },
  methods: {
    setActive() {
      this.isSidebarActive = !this.isSidebarActive;
    },
  },
};
</script>

<style lang="scss" scoped>
.hamburger {
  position: absolute;
  margin: 20px 0;
  transition: transform 0.3s 0.1s ease-in-out;
}

.hamburger--active {
  transform: translateX(calc(100vw - 80px));
}

.home {
  display: flex;
  flex-direction: column;
  justify-content: center;
  height: 100%;
}

.home__name {
  margin: 0;
  color: #ffffff;
  font-weight: lighter;
  text-align: center;
}

.tech-icons {
  margin-top: 20px;
  text-align: center;
}

.tech-icon {
  margin: 5px;

  @media (min-width: 475px) {
    margin: 50px;
  }
}
</style>
