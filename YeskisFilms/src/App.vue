<script setup>
import NavBarVue from "./components/NavBar.vue";
import AboutViewVue from "./views/AboutView.vue";
import GalleryViewVue from "./views/GalleryView.vue";
import ContactViewVue from "./views/ContactView.vue";
import HomeViewVue from "./views/HomeView.vue";
</script>

<template>
  <NavBarVue :opt="opt" :lang="lang" @new-language="handleLang"/>
  <HomeViewVue />
  <AboutViewVue :lang="lang"/>
  <GalleryViewVue :lang="lang"/>
  <ContactViewVue :lang="lang"/>
</template>

<script>
export default {
  methods: {
    handleLang: function() {
      if (this.lang === "Es") {
        this.lang = "En"
      } else [
        this.lang = "Es"
      ]

      console.log(this.lang)
    }
  },
  data() {
    return {
      opt: [
        {
          title: 'Es / En',
          link: "#",
        }
      ],
      lang: "Es"
    }
  }
}
</script>

<style>
html {
  background-color: #222;
  height: 90vh;
  scroll-behavior: smooth;
}
</style>