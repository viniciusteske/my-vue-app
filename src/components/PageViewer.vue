<template>
    <div class="container">
        <h1>{{page.pageTitle}}</h1>
        <div v-html="formattedContent"></div>
    </div>
</template>

<script>
export default {
    props: {
        page: {
            type: Object,
            default() {
                return {
                    pageTitle: '',
                    content: ''
                };
            }
        }
    },
    computed: {
        formattedContent(){
            //Substitui as quebras de linha por <br>
            return this.page.content.replace(/\n/g, '<br>');
        }
    }
}
</script>