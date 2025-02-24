<template>
  <div class="stats-container">
    <h3 v-if="title" class="stats-title">{{ title }}</h3>
    <div class="stats-value">{{ count }}</div>
    <p v-if="description" class="stats-description">{{ description }}</p>
    <div class="stats-controls">
      <button @click="increment" class="control-button increment">
        <span class="button-text">+</span>
      </button>
      <button @click="decrement" class="control-button decrement">
        <span class="button-text">-</span>
      </button>
    </div>
  </div>
</template>

<script setup lang="ts">
const props = defineProps({
  title: {
    type: String,
    default: ''
  },
  description: {
    type: String,
    default: ''
  }
})

const count = ref(12) // Starting with a reasonable number for medical fields

const increment = () => {
  count.value++
}

const decrement = () => {
  count.value--
}
</script>

<style scoped>
.stats-container {
  background: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(10px);
  border-radius: 1rem;
  padding: 2rem;
  margin: 2rem 0;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  text-align: center;
  transition: transform 0.2s ease;
}

.stats-container:hover {
  transform: translateY(-5px);
}

.stats-title {
  color: #4F46E5;
  font-size: 1.5rem;
  margin: 0 0 1rem 0;
}

.stats-value {
  font-size: 3.5rem;
  font-weight: bold;
  color: #1F2937;
  margin: 1rem 0;
}

.stats-description {
  color: #6B7280;
  font-size: 1rem;
  margin: 0.5rem 0 1.5rem 0;
}

.stats-controls {
  display: flex;
  gap: 1rem;
  justify-content: center;
}

.control-button {
  background: #4F46E5;
  color: white;
  border: none;
  border-radius: 0.5rem;
  width: 40px;
  height: 40px;
  cursor: pointer;
  transition: all 0.2s ease;
  display: flex;
  align-items: center;
  justify-content: center;
}

.control-button:hover {
  background: #4338CA;
  transform: scale(1.05);
}

.button-text {
  font-size: 1.5rem;
  font-weight: bold;
}

.decrement {
  background: #DC2626;
}

.decrement:hover {
  background: #B91C1C;
}
</style>
