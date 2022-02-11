<template>
    <div class="app">
        <h4>Создание поста</h4>
        <form>
            <input
                v-bind:value="title"
                @input="title = $event.target.value"
                class="input"
                type="text"
                placeholder="Название"
            />
            <input
                v-bind:value="body"
                class="input"
                type="text"
                placeholder="Описание" />
            <button class="button" @click="createPost">Создать пост</button>
        </form>
        <br>
        <hr>
        <br>
        
        <div v-for="post in posts" v-bind:key="post" class="post">
            <div><strong>Название:</strong>{{ post.title }}</div>
            <div><strong>Описание:</strong>{{ post.body }}</div>
        </div>
    </div>
</template>

<script>
export default {
  data(){
    return{
     posts:[
         {id:1,title:'JavaScript',body:'Описание поста'},
         {id:2,title:'JavaScript 2',body:'Описание поста 2'},
         {id:3,title:'JavaScript 3',body:'Описание поста 3'},
         {id:4,title:'JavaScript 4',body:'Описание поста 4'},
         {id:4,title:'JavaScript 4',body:'Описание поста 4'},
         {id:4,title:'JavaScript 4',body:'Описание поста 4'},
         {id:4,title:'JavaScript 4',body:'Описание поста 4'},
     ],
        title:'',
        body:'',
    }
  },
    methods:{
        createPost(){

        },
        inputTitle(event){
            console.log(event)
        }
    },
  name: 'App',
}
</script>

<style>
    *{
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
    .post{
        padding: 15px;
        border: 2px solid #2c3e50;
        margin-top: 15px;
    }

    .input{
        width: 100%;
        border: 1px solid #2c3e50 ;
        padding: 10px 15px;
        margin-top: 15px;
    }
    .app{
        padding: 20px;
    }
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


</style>
