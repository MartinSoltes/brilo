<template>
    <header>
        <nav class="navbar navbar-expand-lg fixed-top" aria-label="Main navigation">
            <div class="container">
                <a class="navbar-brand" href="#">
                    <img src="../assets/images/Logo.svg" alt="Brilo" width="136" height="48">
                </a>

                <button class="navbar-toggler p-0 border-0"
                    type="button"
                    id="navbarSideCollapse"
                    aria-label="Toggle navigation"
                    @click="toggleMobileNavigation"
                >
                    <span class="navbar-toggler-icon"></span>
                </button>

                <div v-if="navigation" class="navbar-collapse offcanvas-collapse" id="navbarsExampleDefault" :class="{'open': mobileNavigationVisible}">
                    <ul class="navbar-nav ms-auto">
                        <li class="nav-item" v-for="(navItem, index) in navigation" :key="index">
                            <a :href="navItem.link"
                                class="button-link"
                                :class="{'has-submenu': navItem.submenu}"
                            >
                                {{ navItem.title }}
                                <img v-if="navItem.submenu" src="../assets/images/icon-down-green.svg" alt="arrow down" class="icon">
                            </a>
                            <ul v-if="navItem.submenu" class="dropdown-menu">
                                <li v-for="subnavItem in navItem.submenu" :key="subnavItem">
                                    <a class="dropdown-item" :href="subnavItem.link">{{ subnavItem.title }}</a>
                                </li>
                            </ul>
                        </li>
                    </ul>

                </div>
            </div>
        </nav>
    </header>
</template>

<script>

export default {
    name: 'Header',
    methods: {
        toggleMobileNavigation () {
            this.mobileNavigationVisible = !this.mobileNavigationVisible;
        }
    },
    data() {
        return {
            navigation: [
                {
                    title: 'O nás',
                    link: '#'
                },
                {
                    title: 'Služby',
                    link: '#',
                    submenu: [
                        {
                            title: "Submenu 1",
                            link: "#"
                        },
                        {
                            title: "Submenu 2",
                            link: "#"
                        },
                        {
                            title: "Submenu 3",
                            link: "#"
                        }

                    ]
                },
                {
                    title: 'Aktuality',
                    link: '#'
                },
                {
                    title: 'Novinky',
                    link: '#'
                },
                {
                    title: 'Kontakty',
                    link: '#'
                }
            ],
            mobileNavigationVisible: false,
        }
    }
}
</script>

<style lang="less">

</style>