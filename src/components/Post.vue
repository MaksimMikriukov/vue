<template>
  <div class="post">
    <div>
      <h3><strong>{{post.title}}</strong></h3>
      <a>{{post.body}}</a>
    </div>
    <div>
      <Button @click="$emit('remove', post)">Удалить</Button>
    </div>
  </div>
</template>

<script>
import Button from "@/components/UI/Button.vue";

export default {
  name: "Post",
  components: {Button},
  props: {
    post: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.post{
  padding: 15px;
  border-radius: 10px;
  background: #333333;
  margin-block: 30px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>