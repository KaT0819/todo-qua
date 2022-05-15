<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title class="absolute-center"> Todo </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-footer>
      <q-tabs>
        <q-route-tab
          v-for="l in essentialLinks"
          :key="l.title"
          :href="l.link"
          :icon="l.icon"
          :label="l.title"
        />
      </q-tabs>
    </q-footer>

    <q-drawer
      v-model="leftDrawerOpen"
      :breakpoint="766"
      :width="200"
      show-if-above
      bordered
      class="bg-primary"
    >
      <q-list dark>
        <q-item-label header> ナビ </q-item-label>

        <!-- <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
          exact
          clickable
        /> -->

        <q-item
          v-for="link in essentialLinks"
          :key="link.title"
          :to="link.link"
          exact
          clickable
        >
          <q-item-section v-if="link.icon" avatar>
            <q-icon :name="link.icon" />
          </q-item-section>

          <q-item-section>
            <q-item-label>{{ link.title }}</q-item-label>
            <q-item-label caption>{{ link.caption }}</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
// import EssentialLink from 'components/EssentialLink.vue';

const linksList = [
  {
    title: 'Todo',
    caption: '',
    icon: 'list',
    link: '/',
  },
  {
    title: 'Settings',
    caption: '',
    icon: 'settings',
    link: '/settings',
  },
  {
    title: 'Docs',
    caption: 'quasar.dev',
    icon: 'school',
    link: 'https://quasar.dev',
  },
];

export default defineComponent({
  name: 'MainLayout',

  // components: {
  //   EssentialLink,
  // },

  setup() {
    const leftDrawerOpen = ref(false);

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value;
      },
    };
  },
});
</script>

<style lang="scss">
@media screen and (min-width: 468px) {
  .q-footer {
    display: none;
  }
  .q-drawer {
    .q-router-link--exact-active {
      color: white !important;
    }
  }
}
</style>
