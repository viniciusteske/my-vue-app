<template>
   <nav-bar
        :pages="pages"
        :active-page="activePage"
        :nav-link-click="(index) => activePage = index"
    ></nav-bar>
    <page-viewer
        :page="pages[activePage]"></page-viewer>
</template>

<script>
import PageViewer from './components/PageViewer.vue';
import NavBar from './components/NavBar.vue';

export default {
    components: {
        PageViewer,
        NavBar,
    },
    data() {
        return {
            activePage: 0,
            pages: [
                {
                    link: {text: 'Home', url: 'index.html'},
                    pageTitle: 'Home Page',
                    content: 'This is the home content'
                },
                {
                    link: {text: 'About', url: 'about.html'},
                    pageTitle: 'About Page',
                    content: 'This is the about content'
                },
                {
                    link: {text: 'Contact', url: 'contact.html'},
                    pageTitle: 'Contact Page',
                    content: 'This is the contact content'
                }
            ]
        };
    }
}
</script>