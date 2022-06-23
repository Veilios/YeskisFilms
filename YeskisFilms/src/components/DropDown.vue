<template>
    <div class="menu-item" @click="isOpen = !isOpen">
        <a href="#">
            {{ title }}
        </a>
        <svg viewBox="0 0 1030 638" width="10">
            <path d="M1017 68L541 626q-11 12-26 12t-26-12L13 68Q-3 49 6 24.5t39 0h952q24 0 33 24.5t-7 43.5z"
                fill="#FFF">
            </path>
        </svg>

        <transition name="fade" appear>
            <div class="sub-menu" v-if="isOpen">
                <div v-for="(op, i) in opt" :key="i">
                    <a :href="op.link" @click="sendLang">{{ op.title }}</a>
                </div>
            </div>
        </transition>
    </div>
</template>

<script>
export default {
    name: 'dropdown',
    props: ['title', 'opt', "lang"],
    methods: {
        sendLang: function () {
            this.$emit("changing-language")
        }
    },
    data() {
        return {
            isOpen: false
        }
    }
}
</script>

<style>
.menu-item a {
    padding-right: 0.4rem;
}

.menu-item .sub-menu {
    position: absolute;
    display: flex;
    flex-direction: column;
    height: 2.5rem;
    margin-top: 1rem;
    justify-content: space-evenly;
    /* background: linear-gradient(transparent, #235789); */
    background-color: #235789;
    box-shadow: 0 0 5px 10px #235789;
    width: 100%;
    border-radius: 3px;
    padding-left: 1rem;
}

@media (max-width:992px) {
    .menu-item a {
        margin: 0;
        text-align: center;
    }

    .menu-item .sub-menu {
        background-color: none;
        box-shadow: none;
    }
}
</style>