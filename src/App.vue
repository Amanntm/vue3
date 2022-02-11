<template>
    <div class="app">
        <h4>Создание поста</h4>
      <post-form @create="createPost"/><!-- получаем данные из компоненты postForm -->
        <br>
        <hr>
        <br>
        <post-list :posts="posts"/><!-- отправляем данные в компоненту postList -->
    </div>
</template>

<script>

    import PostForm from "./components/PostForm";
    import PostList from "./components/PostList";
    export default {
    components:{
        PostForm,PostList
    },
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
     ]
    }
  },
    methods:{
      createPost(post){
         this.posts.push(post);
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
    .app{
        padding: 20px;
    }


</style>
