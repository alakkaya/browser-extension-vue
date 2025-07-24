<script setup lang="ts">
import type { FilterButtons } from "@/lib/types";
import { useStoreExtension } from "@/stores/storeExtensions";

type ButtonGroup = {
  label: string;
  value: FilterButtons;
};

const store = useStoreExtension();

function handleClick(value: FilterButtons) {
  switch (value) {
    case "all":
      store.activeFilter = "all";
      break;
    case "active":
      store.activeFilter = "active";
      break;
    case "inactive":
      store.activeFilter = "inactive";
      break;
  }
}

const buttonGroup: ButtonGroup[] = [
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
      @click="handleClick(button.value)"
      class="button text-preset-3"
      :class="{ active: store.activeFilter === button.value }"
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

    &.active {
      background-color: var(--switch-btn-bg-color);
      color: var(--bg-neutral-800);
      border-color: transparent;
    }
  }

  & .text-preset-3 {
    color: var(--title-color);
  }
}
</style>
