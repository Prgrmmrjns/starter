<template>
  <div class="page-wrapper">
    <div class="content-container">
      <slot></slot>
    </div>
  </div>
</template>

<style scoped>
.page-wrapper {
  min-height: 100vh;
  background-image: url('ai_medicine.jpg');
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
  position: relative;
}

.page-wrapper::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(5px);
}

.content-container {
  position: relative;
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
}
</style> 