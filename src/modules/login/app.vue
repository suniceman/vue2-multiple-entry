<template>
    <div id="app">
        <nav-component :current="2" />
        <modules :topics="topics" :page="page" :title="title" :loading="loading" />
    </div>
</template>
<script>
import navComponent from '~components/nav-component.vue'
import modules from '~components/modules'
import api from '~api'

export default {
    name: 'index-app',
    components: {
        navComponent,
        modules
    },
    data() {
        return {
            page: Number(new URLSearchParams(window.location.search).get('page')) || 1,
            topics: [],
            title: '登录模块',
            loading: true
        }
    },
    async mounted() {
        const { success, data } = await api.get('topics', { page: this.page })
        if (success) {
            this.topics = data
            this.loading = false
        }
    },
    metaInfo: {
        title: '模块2'
    }
}
</script>
