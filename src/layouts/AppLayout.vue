<script setup lang="ts"></script>
<template>
    <header>
        <slot name="header"></slot>
    </header>
    <main>
        <slot name="main"></slot>
    </main>
</template>

<style scoped>
header {
    margin-top: var(--sp-40);
}

main {
    margin-top: var(--sp-64);
    margin-bottom: var(--sp-64);
}
</style>