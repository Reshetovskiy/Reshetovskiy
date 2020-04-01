<template>
    <header class="header container">
        <a href="/" class="brand link">
            <img src="../assets/images/logo.svg" alt="" class="brand__logo">
            <span class="brand__name">mamon</span>
        </a>
        <nav class="navbar">
            <transition name="fade"  v-if="windowWidth < 767"> 
                <i class="material-icons menu burger" v-if="!show" @click="show = !show">menu</i>
                <i class="material-icons menu burger" v-else @click="show = !show">clear</i>
            </transition>
            <transition name="fade">
                <ul v-if="show" class="header-menu">
                    <li class="header-menu__item" v-for="(item, index) in navLinks" :key="index">
                        <nuxt-link active-class="active" class="header-menu__link link" :to="item.link">{{item.title}}</nuxt-link>
                    </li>
                </ul>
            </transition>
        </nav>
    </header>
</template>

<script>
    export default {
        data: () => ({
            navLinks: [
                {
                    link: '/#services',
                    title: 'Services'
                }, 
                {
                    link: '/#clients',
                    title: 'Clients'
                }, 
                {
                    link: '/#team',
                    title: 'Our team'
                },
                {
                    link: '/#contact', 
                    title: 'Contact Us'
                }
            ],
            show: true, 
            windowWidth: 0,
        }), 
        mounted() {
            window.addEventListener('resize', this.handleResize);
            this.handleResize();
        },
        destroyed() {
            window.removeEventListener('resize', this.handleResize);
        },
        methods: {
            handleResize() {
                this.windowWidth = window.innerWidth;
                this.windowWidth < 767 ? this.show = false : this.show = true
            }
        }
    }
</script>

<style>

</style>