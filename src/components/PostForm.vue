<template>
  <form @submit.prevent>
    <div class="container">
      <h1><strong>Создать пост</strong></h1>
      <textarea
          v-model="post.title"
          placeholder="Название поста"></textarea>
      <textarea
          v-model="post.body"
          placeholder="Описание поста"></textarea>
      <Button @click="createPost">Опубликовать</Button>
    </div>
  </form>
</template>

<script>
import Button from "@/components/UI/Button.vue";

export default {
  name: "PostForm",
  components: {Button},
  data() {
    return {
      post: {
        title: '',
        body: '',
      }
    }
  },
  methods: {
    createPost(){
      if (this.post.title && this.post.body){
        this.post.id = Date.now()
        this.$emit('create', this.post)
        this.post = {
          title: '',
          body: ''
        }
      }
    }
  }
}
</script>

<style scoped>
.container{

}
textarea{
  background: #575757;
  border-radius: 10px;
  border: 1px solid #575757;
  padding: 5px;
  margin: 5px 0px;
  padding-left: 10px;
  color: #e5e5e5;
  resize: none;
  font-size: 16px;
  width: 100%;
  height: 60px;
}
</style>