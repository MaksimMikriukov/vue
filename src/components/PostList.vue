<template>
  <h1><strong>Ваши посты</strong></h1>
  <Post
      v-for="post in posts"
      :post="post"
      :key="post.id"
      @remove="$emit('remove', post)"
  />


</template>

<script>
import Post from "@/components/Post.vue";

export default {
  name: "PostList",
  components: {Post},
  props: {
    posts: {
      type: Array,
      required: true,
    }
  }
}
</script>

<style scoped>

</style>