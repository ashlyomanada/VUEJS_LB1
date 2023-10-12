<template>
  <nav>
    <div class="logo-container">
      <h1>Sign up</h1>
    </div>
    <div class="nav-links" :style="{ left: isActive ? '0%' : '-100%' }">
      <router-link to="/" @click="toggleMenu">Home</router-link>
      <router-link to="/manage" @click="toggleMenu">Manage</router-link>
    </div>
    <button class="hamburger-menu" @click="toggleMenu">
      <img class="png" :src="require('@/assets/more.png')" alt="" />
    </button>
  </nav>
  <div id="app">
    <v-app>
      <router-view> </router-view>
    </v-app>
  </div>
</template>
<style scoped>
nav {
  padding: 30px 0;
  position: fixed;
  height: 10vh;
  width: 100%;
  top: 0;
  left: 0;
  z-index: 1;
  background: #e0ecfb;
  display: flex;
  justify-content: space-around;
  align-items: center;
}

nav a {
  font-weight: bold;
  color: black;
  text-decoration: none;
}
.nav-links {
  display: flex;
  gap: 2rem;
}
.hamburger-menu {
  display: none;
}
nav a.router-link-exact-active {
  color: #005ce6;
}

@media screen and (max-width: 768px) {
  .nav-links {
    position: absolute;
    height: 90vh;
    width: 100vw;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    top: 10vh;
    background: #e0ecfb;
    left: -100%;
    transition: ease 0.3s;
  }
  .hamburger-menu {
    display: unset;
    height: 5vh;
    display: flex;
    align-items: center;
  }
  .png {
    height: 100%;
  }
}
</style>
<script>
import Cookies from "js-cookie";

export default {
  name: "App",

  data() {
    return {
      deferredPrompt: null,
      isActive: false,
    };
  },

  methods: {
    toggleMenu() {
      this.isActive = !this.isActive;
    },
  },
};

/*  created() {
    window.addEventListener("beforeinstallprompt", (e) => {
      e.preventDefault();

      // Stash the event so it can be triggered later.

      this.deferredPrompt = e;

      if (Cookies.get("add-to-home-screen") === undefined) {
        this.deferredPrompt = e;
      }
    });

    window.addEventListener("appinstalled", () => {
      this.deferredPrompt = null;
    });
  },

  methods: {
    async dismiss() {
      Cookies.set("add-to-home-screen", null, { expires: 15 });

      this.deferredPrompt = null;

      this.deferredPrompt = null;
    },

    async install() {
      this.deferredPrompt.prompt();
    },

    toggleMenu() {
      this.isActive = !this.isActive;
    },
  },*/
</script>
