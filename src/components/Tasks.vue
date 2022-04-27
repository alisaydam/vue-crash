<template>
  <div>
    <div :key="task.id" v-for="task in tasks">
      <Task
        @toggle-reminder="$emit('toggle-reminder', task.id)"
        v-bind:task="task"
        @delete-task="$emit('delete-task', task.id)"
      />
    </div>
  </div>
</template>

<script>
import Task from "./Task";
export default {
  name: "Tasks",

  props: {
    tasks: Array,
  },
  components: {
    Task,
  },
  emits: ["delete-task", "toggle-reminder"],
};
</script>