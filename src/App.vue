<script setup lang="ts">
import AppLayout from "@/layouts/AppLayout.vue";
import AppHeader from "./components/app-header.vue";
import ExtensionsHeader from "./components/extensions-header.vue";
import ExtensionsCards from "./components/extensions-cards.vue";
</script>
<!-- Prop Drilling:
  Bir veriyi veya fonksiyonu en üstteki bileşenden en alttaki bileşene kadar, 
  aradaki tüm bileşenlerden prop olarak geçirmek zorunda kalmaktır.
  Yani, veriyi doğrudan ihtiyacı olan bileşene veremeyip, 
  aradaki her bileşene de iletmek gerekir; bu da kodun okunmasını ve yönetimini zorlaştırır.
-->
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
