<template>
    <div class="container mb-3">
        <form action="">
            <div class="mb-3">
                <label for="" class="form-label">
                    Título
                </label>
                <input
                    type="text"
                    class="form-control"
                    v-model="pageTitle"
                />
            </div>
            <div class="mb-3">
                <label for="" class="form-label">
                    Conteúdo
                </label>
                <textarea
                    type="text"
                    class="form-control"
                    rows="5"
                    v-model="content"
                ></textarea>
            </div>
            <div class="mb-3">
                <button
                    class="btn btn-primary"
                    @click.prevent="pageCreated({pageTitle, content})"
                >Postar</button>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    props: ['pageCreated'],
    data () {
        return {
            pageTitle: '',
            content: ''
        }
    }
}
</script>