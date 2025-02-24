<template>
  <div class="home-page">
    <HomeHero
      title="AI in Medicine: The Future of Healthcare"
      description="Welcome to a journey through the revolutionary intersection of Artificial Intelligence and Medical Science. Discover how AI is transforming healthcare delivery and improving patient outcomes."
    >
      <template #actions>
        <button class="hero-button primary" @click="navigateTo('/research')">
          Explore Research
        </button>
        <button class="hero-button secondary" @click="navigateTo('/llms_rare_diseases')">
          Learn More
        </button>
      </template>
    </HomeHero>

    <ContentDoc />
  </div>
</template>

<style scoped>
.home-page {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
}

.hero-button {
  padding: 1rem 2rem;
  border-radius: 0.75rem;
  font-weight: 600;
  font-size: 1rem;
  transition: all 0.2s ease;
  cursor: pointer;
}

.hero-button.primary {
  background: #4F46E5;
  color: white;
  border: none;
}

.hero-button.primary:hover {
  background: #4338CA;
  transform: translateY(-2px);
}

.hero-button.secondary {
  background: transparent;
  color: #4F46E5;
  border: 2px solid #4F46E5;
}

.hero-button.secondary:hover {
  background: rgba(79, 70, 229, 0.1);
  transform: translateY(-2px);
}

@media (max-width: 768px) {
  .home-page {
    padding: 1rem;
  }
}
</style> 