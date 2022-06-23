<template>
    <header>

        <!-- Spanish version -->
        <div class="wrapper" v-if="lang === 'Es'">
            <label for="toggle">&#9776;</label>
            <input type="checkbox" id="toggle">

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

        <!-- English Version -->
        <div class="wrapper" v-if="lang === 'En'">
            <label for="toggle">&#9776;</label>
            <input type="checkbox" id="toggle">

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
    width: 100%;
    height: 30px;
    background-color: #235789;
    box-shadow: 0 0 10px 10px #235789;
    z-index: 1;
}

nav a {
    text-decoration: none;
    padding: 0 1rem;
    color: white;
    animation: fadeInRight 1s ease-in-out;
    clear: right;
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

label {
    margin: 0 15px 0 0;
    font-size: 26px;
    color: white;
    display: none;
    width: 26px;
    float: right;
    position: fixed;
}

#toggle {
    display: none;
}

@media (max-width:992px) {

    .wrapper {
        display: flex;
        flex-direction: column;
        align-items: flex-end;
    }

    label {
        display: flex;
        cursor: pointer;
        z-index: 2;
    }

    nav {
        justify-content: center;
        align-self: flex-end;
        width: 100%;
        display: none;
        background-color: #235789;
        height: 250px;
    }

    nav a {
        display: flex;
        margin: 0;
        padding-top: 10px;
        animation: fadeIn 0.5s ease-in both;
    }

    nav a:nth-child(2) {
        animation-delay: 0.5s;
    }

    nav a:nth-child(3) {
        animation-delay: 1s;
    }

    nav a:nth-child(4) {
        animation-delay: 1.5s;
    }

    nav a:nth-child(5) {
        animation-delay: 2s;
    }

    nav a:not(:first-child) {
        border-left: none;
    }

    @keyframes fadeIn {
        from {
            opacity: 0;
            transform: translate3d(0, -20%, 0);
        }

        to {
            opacity: 1;
            transform: translate3d(0, 0, 0);
        }
    }

    svg {
        display: none;
    }

    #toggle:checked+nav {
        display: flex;
        flex-direction: column;
    }
}
</style>