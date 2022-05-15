<template>
  <q-page class="q-pa-md">
    <q-list bordered separator>
      <!-- <q-separator spaced /> -->

      <q-item
        v-for="t in tasks"
        :key="t.id"
        @click="t.completed = !t.completed"
        clickable
        :class="!t.completed ? 'bg-orange-1' : 'bg-green-1'"
        v-ripple
      >
        <q-item-section side top>
          <q-checkbox v-model="t.completed" />
        </q-item-section>

        <q-item-section>
          <q-item-label :class="{ 'text-strikethrough': t.completed }">
            {{ t.name }}
          </q-item-label>
        </q-item-section>

        <q-item-section side>
          <div class="row">
            <div class="column justify-center">
              <q-icon name="event" size="18px" class="q-mr-xs" />
            </div>
            <div class="column">
              <q-item-label caption class="row justify-end">
                {{ t.dueDate }}
              </q-item-label>
              <q-item-label caption class="row justify-end">
                <small>{{ t.dueTime }}</small>
              </q-item-label>
            </div>
          </div>
        </q-item-section>
      </q-item>
    </q-list>
  </q-page>
</template>

<script lang="ts">
// import { Todo } from 'components/models';
import { defineComponent, ref } from 'vue';
// import ExampleComponent from 'components/ExampleComponent.vue';

export default defineComponent({
  name: 'TodoPage',
  // components: { TaskItem },
  setup() {
    const tasks = ref([
      {
        id: 1,
        name: 'Go to show',
        completed: false,
        dueDate: '2022/05/09',
        dueTime: '09:00',
      },
      {
        id: 2,
        name: 'Get flower',
        completed: true,
        dueDate: '2022/05/12',
        dueTime: '11:30',
      },
      {
        id: 3,
        name: 'Eat Udon',
        completed: false,
        dueDate: '2022/05/23',
        dueTime: '15:20',
      },
    ]);

    const check1 = ref(true);
    const check2 = ref(false);
    const check3 = ref(false);

    return {
      tasks,
      check1,
      check2,
      check3,
    };
  },
});
</script>

<style>
.text-strikethrough {
  text-decoration: line-through;
}
</style>
