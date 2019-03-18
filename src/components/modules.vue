<template>
    <div class="body">
        <div class="loading-layer" v-if="loading">
            <div class="loading"></div>
        </div>
        <div class="header">{{ title }}</div>
        <ul class="topics">
            <li v-for="item in topics" :key="item.id"><a :href="`../view?id=${item.id}`" v-text="item.title" target="_blank"></a></li>
        </ul>
        <div class="pages">
            <a v-if="page > 1" :href="`?page=${page - 1}`">上一页</a> <a v-else href="javascript:;">上一页</a>
            <a :href="`?page=${page + 1}`">下一页</a>
        </div>
    </div>
</template>
<script>
export default {
    props: {
        topics: {
            type: Array,
            default: () => []
        },
        page: {
            default: 1
        },
        title: {
            type: String,
            default: () => '神秘的外星模块'
        },
        loading: {
            type: Boolean,
            default: () => true
        }
    }
}
</script>
