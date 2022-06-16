<script setup>
</script>

<template>
    <header>
        <div class="wrapper">
            <nav>
                <a href="#home">Home</a>
                <a href="#about">About</a>
                <a href="#gallery">Gallery</a>
                <a href="#contact">Contact</a>
                <DropDownVue title="Lang" :items="lang" />
            </nav>
        </div>
    </header>

    <RouterView />
</template>

<script>
import DropDownVue from './DropDown.vue';

export default {
    name: 'navbar',
    components: {
        DropDownVue
    },
    data() {
        return {
            lang: [
                {
                    title: 'Es',
                    link: "#",
                    active: true
                },
                {
                    title: 'En',
                    link: "#",
                    active: false
                }
            ]
        }
    }
}
</script>

<style>
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