<script setup lang="ts">
import ExtensionsCard from "./extensions-card.vue";

// const cards = ref<Extension[]>(extensions);
// Ref? Vue.js'de reaktif bir değişken oluşturur.
// extensions'dan gelen verileri tutmak için kullanılır.
// Bu, bileşenin içinde kullanılacak kart verilerini saklar.
</script>

<template>
  <div class="container">
    <section>
      <div class="cards-grid">
        <ExtensionsCard />
      </div>
    </section>
  </div>
</template>
<style scoped>
.cards-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: var(--sp-12);
}
</style>
