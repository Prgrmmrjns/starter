<template>
  <div class="research-card" :class="{ 'research-card-hover': isHovered }" @mouseenter="isHovered = true" @mouseleave="isHovered = false">
    <div class="research-card-icon">
      <slot name="icon">
        <svg class="default-icon" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M12 22C17.5228 22 22 17.5228 22 12C22 6.47715 17.5228 2 12 2C6.47715 2 2 6.47715 2 12C2 17.5228 6.47715 22 12 22Z" stroke="currentColor" stroke-width="2"/>
          <path d="M15 9L9 15M9 9L15 15" stroke="currentColor" stroke-width="2" stroke-linecap="round"/>
        </svg>
      </slot>
    </div>
    <h3 class="research-card-title">{{ title }}</h3>
    <p class="research-card-description">{{ description }}</p>
    <ul class="research-card-list">
      <li v-for="(item, index) in items" :key="index" class="research-card-item">
        {{ item }}
      </li>
    </ul>
    <div class="research-card-footer">
      <slot name="footer"></slot>
    </div>
  </div>
</template>

<script setup lang="ts">
const props = defineProps({
  title: {
    type: String,
    required: true
  },
  description: {
    type: String,
    default: ''
  },
  items: {
    type: Array as () => string[],
    default: () => []
  }
})

const isHovered = ref(false)
</script>

<style scoped>
.research-card {
  background: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(10px);
  border-radius: 1.5rem;
  padding: 2rem;
  margin: 1rem 0;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
  border: 1px solid rgba(79, 70, 229, 0.1);
}

.research-card-hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 12px rgba(79, 70, 229, 0.2);
}

.research-card-icon {
  width: 3rem;
  height: 3rem;
  margin-bottom: 1.5rem;
  color: #4F46E5;
}

.default-icon {
  width: 100%;
  height: 100%;
}

.research-card-title {
  color: #1F2937;
  font-size: 1.5rem;
  font-weight: bold;
  margin-bottom: 1rem;
}

.research-card-description {
  color: #6B7280;
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.research-card-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.research-card-item {
  color: #4B5563;
  padding: 0.5rem 0;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.research-card-item::before {
  content: "•";
  color: #4F46E5;
  font-weight: bold;
}

.research-card-footer {
  margin-top: 1.5rem;
  padding-top: 1.5rem;
  border-top: 1px solid rgba(79, 70, 229, 0.1);
}
</style> 