<script setup lang="ts">
import AppLayout from "@/layouts/AppLayout.vue";
import AppHeader from "./components/app-header.vue";
import ExtensionsHeader from "./components/extensions-header.vue";
import ExtensionsCards from "./components/extensions-cards.vue";
</script>

<template>
  <AppLayout>
    <!-- Html -->
    <!-- <template v-slot="header"> -->
    <template #header>
      <AppHeader />
    </template>
    <template #main>
      <ExtensionsHeader />
      <ExtensionsCards />
    </template>
  </AppLayout>
</template>
<style scoped>
/* css */
</style>
