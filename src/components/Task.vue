<template>
<div :id="`task-${index}`" class="tasks">
  <p>
    {{message}}
  </p>
</div>
</template>

<script>
import Draggable from 'plain-draggable';
export default {
  name: "Task",
  props: {
    message: {
      type: String
    },
    index: {
      type: Number
    }
  },
  data(){
    return {
      draggable:undefined,
    }
  },
  mounted() {
    this.draggable = new Draggable(document.querySelector(`#task-${this.index}`))
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.tasks {
  background-color: #f0f0f0;
  width: fit-content;
  align-self: flex-start;
}
</style>
