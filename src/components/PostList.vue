<template>
    <div v-for="post in posts" v-bind:key="post" class="post">
        <div><strong>Название:</strong>{{ post.title }}</div>
        <div><strong>Описание:</strong>{{ post.body }}</div>
    </div>
</template>

<script>
    export default {
        props:{
            posts: {
                type:Array,
                required:true
            }
        },
        name: "PostList"
    }
</script>

<style scoped>
    .post{
        padding: 15px;
        border: 2px solid #2c3e50;
        margin-top: 15px;
    }
</style>