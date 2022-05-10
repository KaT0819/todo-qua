<template>
  <li>
    <div>{{ task.name }}</div>
    <small>{{ task.dueDate }} {{ task.dueTime }}</small>
    <button @click="deleteTask(index)">X</button>
  </li>
</template>

<script>
import { defineComponent, ref } from 'vue';
// import { Todo } from 'components/models';

export default defineComponent({
  props: {
    task: ref,
  },
  setup(props) {
    const a = 'Task setup test';
    console.log(props.task);
    return { a };
  },
});
</script>

<style></style>
