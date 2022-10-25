<template>
  <LanesVue :lanes="lanes" :tasks="tasks" />
</template>

<script>
import LanesVue from "./components/LanesVue.vue";

export default {
  name: "App",
  data() {
    return {
      tasks: [
        { titel: "Learn JavaScript", description: "read a book", status: 0 },
        { titel: "Learn Vue", description: "take a break", status: 1 },
        {
          titel: "Build something awsome",
          description: "eat something",
          status: 0,
        },
      ],
      lanes: [
        {
          id: "lane1",
          status: 0,
          titel: "TODO",
          description: "All tasks you need to do",
        },
        {
          id: "lane2",
          status: 1,
          titel: "WORK IN PROGRESS",
          description: "All tasks currently in progress",
        },
        {
          id: "lane3",
          status: 0,
          titel: "DONE",
          description: "All completed tasks",
        },
      ],
    };
  },
  components: {
    LanesVue,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
