<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="wrapper">
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
        <RouterLink to="/gallery">Gallery</RouterLink>
        <RouterLink to="/contact">Contact</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style>
html {
  background-color: #222;
  height: 90vh;
}

nav {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  padding-right: 1rem;
}

a {
  padding-right: 1rem;
  text-decoration: none;
}
</style>