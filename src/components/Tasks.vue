<template>
  <div>
    <div v-for="task in tasks" :key="task.id">
      <Task
        @delete-task="$emit('delete-task', task.id)"
        :task="task"
      />
    </div>
  </div>
</template>

<script>
  import Task from "./Task.vue";

  export default {
    name: "Tasks",
    props: {
      tasks: Array,
    },
    components: {
      Task,
    },
    emits: ["delete-task"],
  };
</script>
