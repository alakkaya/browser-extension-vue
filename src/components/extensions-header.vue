<script setup lang="ts">
import ButtonGroup from "./button-group.vue";
</script>

<template>
  <header>
    <div class="container">
      <div class="wrapper">
        <h1 class="text-preset-1">Extensions List</h1>
        <ButtonGroup />
      </div>
    </div>
  </header>
</template>

<style scoped>
.wrapper {
  margin-bottom: var(--sp-32);
  display: flex;
  align-items: center;
  justify-content: space-between;

  @media (max-width: 40rem) {
    flex-direction: column;
    align-items: center;
    gap: var(--sp-24);
  }

  & .text-preset-1 {
    color: var(--title-color);
  }
}
</style>
