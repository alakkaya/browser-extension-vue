<script setup lang="ts">
import ButtonGroup from './button-group.vue';


</script>

<template>
    <header>
        <div class="container">
            <div class="wrapper">
                <h1>Extensions List</h1>
                <ButtonGroup />
            </div>
        </div>
    </header>

</template>
<style scoped>
.wrapper {
    display: flex;
    align-items: center;
    justify-content: space-between;
}
</style>
