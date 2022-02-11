<template>
    <form @submit.prevent>
        <input
                v-model="post.title"
                class="input"
                type="text"
                placeholder="Название"
        />
        <input
                v-model="post.body"
                class="input"
                type="text"
                placeholder="Описание" />
        <button
                class="button"
                @click="createPost" >Создать пост</button>
    </form>
</template>
<script>
    export default {
        data(){
            return {
                post:{
                    title:'',
                    body:''
                }
            }
        },
        methods:{
            createPost(){
                this.post.id = Date.now();
                this.$emit('create', this.post);
                this.post = {
                   title:'',
                   body:''
                }
            },
        }
    }
</script>
<style scoped>
    form{
        display: flex;
        flex-direction: column;
    }
    .button{
        background: none;
        margin-top: 15px;
        align-self: flex-end;
        color: #2c3e50;
        padding: 10px;
        align-items: center;
        border: 1px solid #2c3e50;
    }
    .input{
        width: 100%;
        border: 1px solid #2c3e50 ;
        padding: 10px 15px;
        margin-top: 15px;
    }
</style>