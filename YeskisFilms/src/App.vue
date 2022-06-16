<script setup>
import NavBarVue from "./components/NavBar.vue";
import AboutViewVue from "./views/AboutView.vue";
import GalleryViewVue from "./views/GalleryView.vue";
import ContactViewVue from "./views/ContactView.vue";
import HomeViewVue from "./views/HomeView.vue";
</script>

<template>
  <NavBarVue/>
  <HomeViewVue />
  <AboutViewVue />
  <GalleryViewVue />
  <ContactViewVue />
</template>

<script>

</script>

<style>
html {
  background-color: #222;
  height: 90vh;
  scroll-behavior: smooth;
}
</style>