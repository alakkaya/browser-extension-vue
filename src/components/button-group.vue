<script setup lang="ts">
const buttonGroup = [
  {
    label: "All",
    value: "all",
  },
  {
    label: "Active",
    value: "active",
  },
  {
    label: "Inactive",
    value: "inactive",
  },
];
</script>

<template>
  <div class="button-group">
    <button
      class="button text-preset-3"
      v-for="button of buttonGroup"
      :key="button.value"
    >
      {{ button.label }}
    </button>
  </div>
</template>
<style scoped>
.button-group {
  display: flex;
  align-items: center;
  gap: var(--sp-12);

  & .button {
    border: 1px solid var(--border-color);
    border-radius: 999px;
    padding: var(--sp-8) var(--sp-20) var(--sp-10);
    background-color: var(--remove-btn-bg-color);
  }

  & .text-preset-3 {
    color: var(--title-color);
  }
}
</style>
