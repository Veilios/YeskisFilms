<template>
    <header>
        <div class="wrapper">
            <nav>
                <a href="#home">Home</a>
                <a href="#about">About</a>
                <a href="#gallery">Gallery</a>
                <a href="#contact">Contact</a>
                <DropDownVue @click.prevent="" title="Lang" :opt="opt" :lang="lang" @changing-language="newLang"/>
            </nav>
        </div>
    </header>

    <RouterView />
</template>

<script>
import DropDownVue from './DropDown.vue';

export default {
    name: 'navbar',
    props: ['opt', "lang"],
    components: {
        DropDownVue
    },
    methods: {
        newLang: function() {
            this.$emit("new-language");
        }
    }
}
</script>

<style>
nav {
    display: flex;
    align-items: center;
    padding: 1rem;
    position: fixed;
    right: 0;
    top: 0;
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