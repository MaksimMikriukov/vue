<template>
  <div class="app">

    <Dialog v-model:show="dialogVisible">
      <PostForm
          @create="createPost"
      />
    </Dialog>
    <PostList
        :posts="posts"
        @remove="removePost"
    />
    <Button @click="showDialog">Создать пост</Button>
  </div>
</template>

<script>
  import PostList from "@/components/PostList.vue";
  import PostForm from "@/components/PostForm.vue";
  import Dialog from "@/components/UI/Dialog.vue";
  import Button from "@/components/UI/Button.vue";

  export default {
    components: {Button, Dialog, PostForm, PostList},
    data(){
      return{
        posts: [
          {id: 1, title: 'React', body: 'Классный'},
          {id: 2, title: 'Vue', body: 'Клёвый'},
          {id: 3, title: 'Angular', body: 'Кислый'},
        ],
        dialogVisible: false,
      }
    },
    methods: {
      createPost(post){
        this.posts.push(post)
        this.dialogVisible = false
        },
      removePost(post){
        this.posts = this.posts.filter(p => p.id !== post.id)
      },
      showDialog(){
        this.dialogVisible = true;
      }
      },
  }
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Roboto Slab Thin";
}
body{
  background: #171717;
  color: #e5e5e5;
  margin-inline: 30px;
}
form{
  display: block;

}
.app{
  margin-inline: 100px;
}

::-webkit-scrollbar {
  width: 10px;
}
::-webkit-scrollbar-track {
  background-color: darkgrey;
  border-radius: 10px;
}
::-webkit-scrollbar-thumb {
  box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.3);
  border-radius: 10px;
}

::placeholder {
  color: #e5e5e5;
}

@font-face {
  font-family: 'Roboto Slab Thin';
  src: url('fonts/RobotoSlab-Thin.ttf') format('truetype');
  font-style: normal;
  font-weight: 100;
}
</style>