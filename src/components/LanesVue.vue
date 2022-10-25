<template>
  <div class="row">
    <div class="col-md-4 col-xs-12" v-for="lane in lanes" :key="lane.id">
      <div class="card">
        <div class="card-header">
          {{ lane.titel }}
        </div>
        <div class:="card-body">
            <p>{{lane.description}}</p>
        </div>
        <ul class="list-group">
          <li class="list-group-item" v-for="task in tasks.filter((task) => task.status == lane.status)" :key="task.id">
            <h4>{{task.titel}}
            <button type="button" class="btn btn-sm" @click="edit(task)">Edit</button>
            </h4>
            <p>{{task.description}}</p>
            <p><button type="button" class="btn btn-sm" @click="nextState(task)">Next</button></p>
          </li>
        </ul>
      </div>
    </div>
  </div>
  <div v-if="editTask"><EditTaskVue :task="editTask"></EditTaskVue></div>
</template>

<script>
import EditTaskVue from './EditTaskVue.vue';
export default {
  name: "LanesVue",
  data() {
    return {
      editTask: null,
    }
  },
  props: {
    lanes: Array,
    tasks: Array,
  },
  methods: {
    nextState(task) {
      task.status++;
      this.$emit("update-task", task);
    },
    edit(task) {
      console.log(task);
      this.editTask = task;
    }
  },
  components: {
    EditTaskVue,
  }
};
</script>
