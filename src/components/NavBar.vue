<template>
    <nav 
    :class="[`navbar-${theme}`, `bg-${theme}`, 'navbar', 'navbar-expand-lg']"
    style="background-color: #FBBA00;"
    >
    <div class="container-fluid">
        <a class="navbar-brand" href="#">SmartFit</a>
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li v-for="(page, index) in pages " class="nav-item" :key="index">
                <nav-bar-link
                    :page="page"
                    :isActive="activePage == index"
                    @click.prevent="navLinkClick(index)"
                ></nav-bar-link>
            </li>
        </ul>
        <form class="d-flex">
            <button 
                class="btn btn-primary"
                @click.prevent="changeTheme()"
            >Toggle</button>
        </form>
    </div>
</nav>
</template>

<script>
import NavBarLink from './NavBarLink.vue';

export default {
    components: {
        NavBarLink
    },
    created() {
        this.getThemeSetting();
    },
    props: ['pages', 'activePage', 'navLinkClick'],
    data() {
        return {
            theme: 'light'
        }
    },
    methods: {
        changeTheme(){
            let theme = 'light';
            if(this.theme == 'light'){
                theme = 'dark';
            }
            this.theme = theme;
            this.storeThemeSetting();
        },
        storeThemeSetting() {
            localStorage.setItem('theme', this.theme);
        },
        getThemeSetting() {
            let theme = localStorage.getItem('theme');
            if(theme){
                this.theme = theme;
            }
        }
    }
}
</script>