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
      <h1 class="home__name">TECHNOLOGIES</h1>
      <div class="tech-icons">
        <icon
          class="tech-icon"
          v-for="icon in icons"
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
import docker from "@/assets/docker.svg";
import gatsby from "@/assets/gatsby.svg";
import gridsome from "@/assets/gridsome.svg";
import vue from "@/assets/vue.svg";
import react from "@/assets/react.svg";
import python from "@/assets/python.svg";

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
          src: vue,
          href: "https://vuejs.org/",
        },
        {
          src: react,
          href: "https://reactjs.org/",
        },
        {
          src: python,
          href: "https://www.python.org/",
        },
        {
          src: gatsby,
          href: "https://www.gatsbyjs.org/",
        },
        {
          src: gridsome,
          href: "https://gridsome.org/",
        },
        {
          src: docker,
          href: "https://www.docker.com/",
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

<style scoped>
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
  margin: 20px;
}
</style>
