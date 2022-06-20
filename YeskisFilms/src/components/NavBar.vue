<template>
    <header>
        <div class="wrapper" v-if="lang === 'Es'">
            <nav>
                <a href="#home">Inicio</a>
                <a href="#about">Acerca de</a>
                <a href="#portfolio">Portafolio</a>
                <a href="#contact">Contacto</a>
                <a>
                    <DropDownVue @click.prevent="" title="Idioma" :opt="opt" :lang="lang"
                        @changing-language="newLang" />
                </a>
            </nav>
        </div>

        <div class="wrapper" v-if="lang === 'En'">
            <nav>
                <a href="#home">Home</a>
                <a href="#about">About</a>
                <a href="#portfolio">Portfolio</a>
                <a href="#contact">Contact</a>
                <a>
                    <DropDownVue @click.prevent="" title="Lang" :opt="opt" :lang="lang" @changing-language="newLang" />
                </a>
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
    justify-content: flex-end;
    padding: 1rem;
    position: fixed;
    right: 0;
    top: 0;
    z-index: 2;
    width: 100%;
    height: 30px;
    background: linear-gradient(#235789, transparent);
}

a {
    text-decoration: none;
    padding: 0 1rem;
    color: white;
    animation: fadeInRight 1s ease-in-out;
}

@keyframes fadeInRight {
    from {
        opacity: 0;
        transform: translateX(300px);
    }

    to {
        opacity: 1;
    }
}

nav a:hover {
    color: #FB3640;
    transition: ease-in 0.5s;
}

nav a:not(:first-child) {
    border-left: white solid 1px;
}

nav a:last-child {
    padding-left: 0;
}
</style>