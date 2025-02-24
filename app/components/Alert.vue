<template>
  <div class="alert" :style="{ 'border-color': color }">
    <slot></slot>
  </div>
</template>

<script setup lang="ts">
const { color } = defineProps({
  color: {
    type: String,
    default: 'orange'
  }
})
</script>

<style scoped>
.alert {
  display: flex;
  align-items: center;
  padding: 1.5rem;
  border: 2px solid;
  border-radius: 0.75rem;
  background-color: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(10px);
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  margin: 1.5rem 0;
}

.alert:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
}
</style>