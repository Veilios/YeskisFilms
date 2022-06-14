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
  text-decoration: none;
  padding: 0 1rem;
  color: white;
}

nav a:hover {
  color: cyan;
  transition: ease-in 0.5s;
}

nav a:not(:first-child) {
  border-left: white solid 1px;
}
</style>