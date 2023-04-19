<template>
  <div class="dialog" v-if="show" @click="hideDialog">
    <div @click.stop class="dialog_content">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "Dialog",
  props: {
    show:{
      type: Boolean,
      default: false
    }
  },
  methods: {
    hideDialog(){
      this.$emit('update:show', false)
    }
  }
}

</script>

<style scoped>
.dialog{
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  background: rgba(0,0,0,0.5);
  position: fixed;
  display: flex;
}
.dialog_content{
  margin: auto;
  background: #171717;
  border-radius: 10px;
  min-height: 200px;
  min-width: 300px;
  padding: 30px;
}

</style>