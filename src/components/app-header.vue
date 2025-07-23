<script setup lang="ts">
import HeaderLogo from "./header-logo.vue";
import ToggleTheme from "./toggle-theme.vue";
</script>

<template>
  <div class="container">
    <div class="wrapper">
      <HeaderLogo />
      <ToggleTheme />
    </div>
  </div>
</template>

<style scoped>
.wrapper {
  border-radius: var(--sp-20);
  padding: var(--sp-12) var(--sp-16);
  background-color: var(--bg-neutral-800);
  display: flex;
  align-items: center;
  justify-content: space-between;

  @media (max-width: 48rem) {
    padding: var(--sp-8) var(--sp-12);
  }
}
</style>
