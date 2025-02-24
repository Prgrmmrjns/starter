<template>
  <div class="hero-container">
    <div class="hero-content">
      <h1 class="hero-title">{{ title }}</h1>
      <p class="hero-description">{{ description }}</p>
      <div class="hero-stats">
        <div class="stat-item" v-for="stat in stats" :key="stat.label">
          <div class="stat-value">{{ stat.value }}</div>
          <div class="stat-label">{{ stat.label }}</div>
        </div>
      </div>
      <div class="hero-actions">
        <slot name="actions"></slot>
      </div>
    </div>
    <div class="hero-background">
      <div class="hero-shape-1"></div>
      <div class="hero-shape-2"></div>
      <div class="hero-shape-3"></div>
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
    required: true
  },
  stats: {
    type: Array as () => Array<{ value: string | number, label: string }>,
    default: () => []
  }
})
</script>

<style scoped>
.hero-container {
  position: relative;
  padding: 6rem 2rem;
  overflow: hidden;
  background: linear-gradient(135deg, rgba(79, 70, 229, 0.1) 0%, rgba(147, 51, 234, 0.1) 100%);
  border-radius: 2rem;
  margin-bottom: 4rem;
}

.hero-content {
  position: relative;
  z-index: 1;
  max-width: 800px;
  margin: 0 auto;
  text-align: center;
}

.hero-title {
  font-size: 3.5rem;
  font-weight: 800;
  color: #1F2937;
  margin-bottom: 1.5rem;
  line-height: 1.2;
  background: linear-gradient(135deg, #4F46E5 0%, #9333EA 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.hero-description {
  font-size: 1.25rem;
  color: #6B7280;
  margin-bottom: 3rem;
  line-height: 1.8;
}

.hero-stats {
  display: flex;
  justify-content: center;
  gap: 4rem;
  margin-bottom: 3rem;
}

.stat-item {
  text-align: center;
}

.stat-value {
  font-size: 2.5rem;
  font-weight: 700;
  color: #4F46E5;
  margin-bottom: 0.5rem;
}

.stat-label {
  font-size: 1rem;
  color: #6B7280;
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.hero-actions {
  display: flex;
  justify-content: center;
  gap: 1rem;
}

.hero-background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  overflow: hidden;
}

.hero-shape-1,
.hero-shape-2,
.hero-shape-3 {
  position: absolute;
  background: linear-gradient(135deg, #4F46E5 0%, #9333EA 100%);
  border-radius: 50%;
  opacity: 0.1;
}

.hero-shape-1 {
  width: 400px;
  height: 400px;
  top: -200px;
  left: -200px;
}

.hero-shape-2 {
  width: 300px;
  height: 300px;
  top: 50%;
  right: -150px;
  transform: translateY(-50%);
}

.hero-shape-3 {
  width: 200px;
  height: 200px;
  bottom: -100px;
  left: 50%;
  transform: translateX(-50%);
}

@media (max-width: 768px) {
  .hero-container {
    padding: 4rem 1rem;
  }

  .hero-title {
    font-size: 2.5rem;
  }

  .hero-description {
    font-size: 1.125rem;
  }

  .hero-stats {
    flex-direction: column;
    gap: 2rem;
  }

  .stat-value {
    font-size: 2rem;
  }
}
</style> 