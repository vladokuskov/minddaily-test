<template>
    <a href="#/">Home</a> |
    <a href="#/dashboard/diaries">Dashboard</a> |
    <component :is="currentView" />
</template>

<script setup lang="ts">

import Dashboard from "@/components/Dashboard.vue";
import Home from "@/components/Home.vue";
import {computed, ref} from "vue";

const routes = {
  '/': Home,
  '/dashboard/diaries': Dashboard
}

const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || '/']
})

window.addEventListener('hashchange', () => {
  currentPath.value = window.location.hash
})

const currentPath = ref(window.location.hash)
</script>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
