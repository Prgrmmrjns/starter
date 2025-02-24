<template>
  <div class="home-hero">
    <div class="hero-content">
      <h1 class="hero-title">{{ title }}</h1>
      <p class="hero-description">{{ description }}</p>
      <div class="hero-actions">
        <slot name="actions"></slot>
      </div>
    </div>
    <div class="hero-image">
      <img src="/ai_medicine.jpg" alt="AI in Medicine" class="featured-image">
      <div class="image-overlay"></div>
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
  }
})
</script>

<style scoped>
.home-hero {
  position: relative;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2rem;
  padding: 4rem 2rem;
  background: linear-gradient(135deg, rgba(79, 70, 229, 0.1) 0%, rgba(147, 51, 234, 0.1) 100%);
  border-radius: 2rem;
  overflow: hidden;
  margin-bottom: 4rem;
}

.hero-content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  z-index: 1;
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
  margin-bottom: 2rem;
  line-height: 1.8;
}

.hero-actions {
  display: flex;
  gap: 1rem;
}

.hero-image {
  position: relative;
  border-radius: 1.5rem;
  overflow: hidden;
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
  transform: perspective(1000px) rotateY(-5deg);
  transition: transform 0.3s ease;
}

.hero-image:hover {
  transform: perspective(1000px) rotateY(-2deg) translateY(-5px);
}

.featured-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.image-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(135deg, rgba(79, 70, 229, 0.2) 0%, rgba(147, 51, 234, 0.2) 100%);
  pointer-events: none;
}

@media (max-width: 1024px) {
  .home-hero {
    grid-template-columns: 1fr;
    padding: 3rem 1.5rem;
  }

  .hero-title {
    font-size: 2.5rem;
  }

  .hero-description {
    font-size: 1.125rem;
  }

  .hero-image {
    transform: none;
    max-height: 400px;
  }

  .hero-image:hover {
    transform: translateY(-5px);
  }
}
</style> 