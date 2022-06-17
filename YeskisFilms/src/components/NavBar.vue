<template>
    <header>
        <div class="wrapper" v-if="lang === 'Es'">
            <nav>
                <a href="#home">Inicio</a>
                <a href="#about">Acerca de</a>
                <a href="#gallery">Portafolio</a>
                <a href="#contact">Contacto</a>
                <DropDownVue @click.prevent="" title="Idioma" :opt="opt" :lang="lang" @changing-language="newLang" />
            </nav>
        </div>

        <div class="wrapper" v-if="lang === 'En'">
            <nav>
                <a href="#home">Home</a>
                <a href="#about">About</a>
                <a href="#gallery">Portfolio</a>
                <a href="#contact">Contact</a>
                <DropDownVue @click.prevent="" title="Lang" :opt="opt" :lang="lang" @changing-language="newLang" />
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
        newLang: function () {
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