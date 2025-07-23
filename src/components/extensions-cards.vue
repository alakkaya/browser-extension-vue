<script setup lang="ts">
import { extensions } from "@/lib/data";
import type { Extension } from "@/lib/types";

import { ref } from "vue";
import SwitchButton from "./switch-button.vue";

const cards = ref<Extension[]>(extensions);
// Ref? Vue.js'de reaktif bir değişken oluşturur.
// extensions'dan gelen verileri tutmak için kullanılır.
// Bu, bileşenin içinde kullanılacak kart verilerini saklar.
</script>

<template>
  <div class="container">
    <section>
      <div class="cards-grid">
        <article v-for="card of cards" :key="card.id" class="card">
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
            <button class="text-preset-6">Remove</button>
            <SwitchButton />
          </div>
        </article>
      </div>
    </section>
  </div>
</template>
<style scoped>
.cards-grid {
  & .card {
    border: 1px solid var(--border-color);
    border-radius: var(--sp-20);
    padding: var(--sp-20);
    background-color: var(--bg-neutral-800);

    & .card-content {
      margin-bottom: var(--sp-48);
      display: flex;
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
      }
    }
  }
}
</style>
