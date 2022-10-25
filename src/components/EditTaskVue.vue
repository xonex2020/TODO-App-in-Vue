<template>
  <h4>Edit Task</h4>
  <form>
    <input type="text" v-model="titel">
  </form>
</template>

<script>
export default {
  name: "EditTaskVue",      
  props: {
    task: Object,     
  },
  data() {
    return {
      titel: this.task.titel,
      }
  },
  methods: {
    updateTask() {
      this.$emit("update-task", this.task);
    },
},
};
</script>
