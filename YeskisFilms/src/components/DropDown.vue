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
                <div v-for="(item, i) in items" :key="i">
                    <a :href="item.link" v-on:click="item.active = !item.active">{{ item.title }}</a>
                </div>
            </div>
        </transition>
    </div>
</template>

<script>
export default {
    name: 'dropdown',
    props: ['title', 'items'],
    data() {
        return {
            isOpen: false
        }
    }
}
</script>

<style>
.menu-item {
    border-left: solid white 1px;
}

.menu-item a {
    padding-right: 0.4rem;
}

.menu-item .sub-menu {
    position: absolute;
    display: flex;
    flex-direction: column;
    height: 3rem;
    justify-content: space-evenly;
}
</style>