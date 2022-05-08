<template>
  <q-page padding>
    <ul>
      <li v-for="(task, index) in tasks" :key="task.id">
        <div>{{ task.name }}</div>
        <small>{{ task.dueDate }} {{ task.dueTime }}</small>
        <button @click="deleteTask(index)">X</button>
      </li>
    </ul>
  </q-page>
</template>

<script lang="ts">
import { Todo } from 'components/models';
import { defineComponent, ref } from 'vue';
// import ExampleComponent from 'components/ExampleComponent.vue';

export default defineComponent({
  name: 'IndexPage',
  // components: { ExampleComponent },
  setup() {
    const tasks = ref<Todo[]>([
      {
        id: 1,
        name: 'Go to show',
        dueDate: '2022/05/21',
        dueTime: '10:30',
      },
      {
        id: 2,
        name: 'Get flower',
        dueDate: '2022/05/21',
        dueTime: '11:30',
      },
      {
        id: 3,
        name: 'Eat Udon',
        dueDate: '2022/05/21',
        dueTime: '12:30',
      },
    ]);

    const deleteTask = (index: number) => {
      console.log('delete' + index);

      tasks.value.splice(index, 1);
      console.log(tasks);
    };

    return {
      tasks,
      deleteTask,
    };
  },
});
</script>

<style></style>
