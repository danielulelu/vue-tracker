<template>
  <div :class="[task.reminder ? 'reminder' : '', 'task']">
    <h3>
      {{ task.text }}
      <i @click="$emit('delete-task', task.id)" class="fas fa-times"></i>
    </h3>
    <p>{{ task.day }}</p>
  </div>
</template>

<script>
  export default {
    name: "Task",
    props: {
      task: Object,
    },
  };
</script>

<style>
  .fas {
    color: red;
  }
  .task {
    background: #f4f4f4;
    margin: 10px;
    padding: 10px 24px;
    cursor: pointer;
  }
  .task.reminder {
    border-left: 5px solid green;
  }

  .task h3 {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
</style>
