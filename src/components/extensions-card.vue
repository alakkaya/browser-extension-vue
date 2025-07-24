<script setup lang="ts">
import { useStoreExtension } from "@/stores/storeExtensions";
import SwitchButton from "./switch-button.vue";

const store = useStoreExtension();
</script>

<template>
  <TransitionGroup name="card-list" tag="div" class="card-transition-group">
    <article
      v-for="card of store.filteredExtensions"
      :key="card.id"
      class="card"
    >
      <div class="card-content">
        <img :src="card.logo" :alt="`${card.name} logo`" />
        <div class="card-text">
          <h2 class="text-preset-2">{{ card.name }}</h2>
          <p class="text-preset-5">
            {{ card.description }}
          </p>
        </div>
      </div>
      <div class="card-footer">
        <button @click="store.deleteExtension(card.id)" class="text-preset-6">
          Remove
        </button>
        <SwitchButton
          :checked="card.isActive"
          :name="card.name"
          @update:checked="store.toggleExtension(card.id)"
        />
      </div>
    </article>
  </TransitionGroup>
</template>

<style scoped>
& .card {
  border: 1px solid var(--border-color);
  border-radius: var(--sp-20);
  padding: var(--sp-20);
  background-color: var(--bg-neutral-800);

  & .card-content {
    margin-bottom: var(--sp-48);
    display: flex;
    align-items: flex-start;
    gap: var(--sp-16);
    & .card-text {
      & .text-preset-2 {
        margin-bottom: var(--sp-8);
        color: var(--title-color);
      }

      & .text-preset-5 {
        color: var(--text-color);
      }
    }
  }

  & .card-footer {
    display: flex;
    align-items: center;
    justify-content: space-between;

    & .text-preset-6 {
      border-radius: 999px;
      border: 1px solid var(--border-color);
      padding: var(--sp-8) var(--sp-16);
      color: var(--title-color);
      transition: background-color 0.3s, color 0.3s ease-in-out;

      &:hover {
        border-color: transparent;
        background-color: var(--switch-btn-bg-color);
        color: var(--hover-color);
      }
    }
  }
}

.card-transition-group {
  display: contents;
}

.caard-list-enter-active,
.card-list-leave-active {
  transition: all 0.5s ease;
}

.card-list-enter-from {
  opacity: 0;
  transform: translateY(20px);
}

.card-list-leave-to {
  opacity: 0;
  transform: translateY(-20px);
}

.card-list-move {
  transition: transform 0.5s ease;
}
</style>
