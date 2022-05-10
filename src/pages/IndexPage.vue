<template>
  <q-page padding>
    <ul>
      <task-item v-for="task in tasks" :key="task.id" :task="task" />
    </ul>
  </q-page>
</template>

<script lang="ts">
// import { Todo } from 'components/models';
import { defineComponent, ref } from 'vue';
// import ExampleComponent from 'components/ExampleComponent.vue';
import TaskItem from 'src/components/TaskItem.vue';

export default defineComponent({
  name: 'IndexPage',
  components: { TaskItem },
  setup() {
    const tasks = ref([
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
