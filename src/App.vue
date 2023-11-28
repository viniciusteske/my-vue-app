<template>
   <nav-bar
        :pages="pages"
        :active-page="activePage"
        :nav-link-click="(index) => activePage = index"
    ></nav-bar>
    <page-viewer
        v-if="pages.length>0"
        :page="pages[activePage]"
    ></page-viewer>
    <create-page
        :page-created="pageCreated"
    ></create-page>
    <scatter-plot></scatter-plot>
</template>

<script>
import PageViewer from './components/PageViewer.vue';
import NavBar from './components/NavBar.vue';
import CreatePage from './components/CreatePage.vue';
import ScatterPlot from './components/ScatterPlot.vue';

export default {
    components: {
        PageViewer,
        NavBar,
        CreatePage,
        ScatterPlot
    },
    created() {
        this.getPages();
    },
    data() {
        return {
            activePage: 0,
            pages: []
        };
    },
    methods: {
        async getPages() {
            let res = await fetch('pages.json');
            let data = await res.json();

            this.pages = data;
        },
        pageCreated(pageObj) {
            console.log(pageObj);
        }
    }
}
</script>