<template>
 <button>
    <slot></slot>
 </button>
</template>

<script>
export default {
  name: "Button"
}
</script>

<style scoped>
button{
  background: #575757;
  border-radius: 10px;
  border: 1px solid #7c7c7c;
  padding: 3px 5px;
  color: #e5e5e5;
  margin: 5px 0px;
  font-size: 16px;
}
</style>