<script setup lang="ts">
defineProps<{ name: string; checked: boolean }>();

const emit = defineEmits<{
  "update:checked": [boolean];
}>();

const handleChange = (event: Event) => {
  const target = event.target as HTMLInputElement;
  emit("update:checked", target.checked);
};
</script>

<template>
  <label class="switch">
    <input
      type="checkbox"
      :checked="checked"
      @change="handleChange"
      :aria-label="`Toggle ${name} extension`"
    />
    <span class="slider"></span>
  </label>
</template>

<style scoped>
.switch {
  position: relative;
  display: inline-block;
  width: 36px;
  height: 20px;
}

.switch input {
  opacity: 0;
  width: 0;
  height: 0;
}
.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: var(--clr-neutral-600);
  transition: 0.4s;
  border-radius: 34px;
}
.slider:before {
  position: absolute;
  content: "";
  height: 16px;
  width: 16px;
  left: 3px;
  bottom: 2px;
  background-color: white;
  transition: 0.4s;
  border-radius: 50%;
}
input:checked + .slider {
  background-color: var(--switch-btn-bg-color);
}
input:checked + .slider:before {
  transform: translateX(14px);
}
</style>
