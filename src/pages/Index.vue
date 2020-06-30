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
      <h1 class="home__name">KRYSTIAN SIWEK</h1>
      <h2 class="home__small-header">frontend developer</h2>
    </div>
  </Layout>
</template>

<script>
import Navbar from "@/components/Navbar";
import MobileSidebar from "@/components/MobileSidebar";
import Hamburger from "@/components/Hamburger";

export default {
  components: {
    Navbar,
    MobileSidebar,
    Hamburger,
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

.home__name,
.home__small-header {
  margin: 0;
  color: #ffffff;
  font-weight: lighter;
  text-align: center;
}
</style>
