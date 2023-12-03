<template>
   <nav-bar
        :pages="pages"
        :active-page="activePage"
        :nav-link-click="(index) => activePage = index"
    ></nav-bar>
    <div class="centralize">
        <page-viewer
        v-if="pages.length>0"
        :page="pages[activePage]"
        ></page-viewer>
    </div>
    <create-page
        v-if="activePage == 3"
        :page-created="pageCreated"
    ></create-page>
    <div class="charts-container">
        <BarChart 
            v-if="activePage == 0"
        />
        <ScatterChart
            v-if="activePage == 0"
        />
    </div>
</template>

<style>
    .charts-container {
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 20px;
        max-width: 940px;
    }
    .centralize {
        text-align: center;
    }
</style>

<script>
import PageViewer from './components/PageViewer.vue';
import NavBar from './components/NavBar.vue';
import CreatePage from './components/CreatePage.vue';
import BarChart from './components/BarChart.vue';
import ScatterChart from './components/ScatterChart.vue';

export default {
    components: {
        PageViewer,
        NavBar,
        CreatePage,
        BarChart,
        ScatterChart
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