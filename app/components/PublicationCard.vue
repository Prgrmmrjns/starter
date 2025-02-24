<template>
  <div class="publication-card" :class="{ 'publication-card-hover': isHovered }" @mouseenter="isHovered = true" @mouseleave="isHovered = false">
    <div class="publication-meta">
      <span class="publication-date">{{ date }}</span>
      <span class="publication-category" :style="{ backgroundColor: categoryColor + '20', color: categoryColor }">
        {{ category }}
      </span>
    </div>
    <h3 class="publication-title">{{ title }}</h3>
    <p class="publication-authors">{{ authors }}</p>
    <p class="publication-abstract">{{ abstract }}</p>
    <div class="publication-stats">
      <div class="stat">
        <svg class="stat-icon" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M12 21L10.55 19.7C5.4 15.1 2 12.1 2 8.5C2 5.5 4.42 3 7.5 3C9.24 3 10.91 3.81 12 5.09C13.09 3.81 14.76 3 16.5 3C19.58 3 22 5.5 22 8.5C22 12.1 18.6 15.1 13.45 19.7L12 21Z" fill="currentColor"/>
        </svg>
        <span>{{ citations }} citations</span>
      </div>
      <div class="stat">
        <svg class="stat-icon" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M21 11.5C21.0034 12.8199 20.6951 14.1219 20.1 15.3C19.3944 16.7118 18.3098 17.8992 16.9674 18.7293C15.6251 19.5594 14.0782 19.9994 12.5 20C11.18 20.0035 9.87812 19.6951 8.7 19.1L3 21L4.9 15.3C4.30493 14.1219 3.99656 12.8199 4 11.5C4.00061 9.92179 4.44061 8.37488 5.27072 7.03258C6.10083 5.69028 7.28825 4.6056 8.7 3.90003C9.87812 3.30496 11.18 2.99659 12.5 3.00003H13C15.0843 3.11502 17.053 3.99479 18.5291 5.47089C20.0052 6.94699 20.885 8.91568 21 11V11.5Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
        <span>{{ comments }} comments</span>
      </div>
    </div>
    <div class="publication-actions">
      <button class="action-button primary" @click="$emit('view')">
        Read More
      </button>
      <button class="action-button secondary" @click="$emit('download')">
        Download PDF
      </button>
    </div>
  </div>
</template>

<script setup lang="ts">
const props = defineProps({
  title: {
    type: String,
    required: true
  },
  authors: {
    type: String,
    required: true
  },
  abstract: {
    type: String,
    default: ''
  },
  date: {
    type: String,
    required: true
  },
  category: {
    type: String,
    required: true
  },
  categoryColor: {
    type: String,
    default: '#4F46E5'
  },
  citations: {
    type: Number,
    default: 0
  },
  comments: {
    type: Number,
    default: 0
  }
})

const isHovered = ref(false)
</script>

<style scoped>
.publication-card {
  background: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(10px);
  border-radius: 1.5rem;
  padding: 2rem;
  margin: 1.5rem 0;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
  border: 1px solid rgba(79, 70, 229, 0.1);
}

.publication-card-hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 12px rgba(79, 70, 229, 0.2);
}

.publication-meta {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 1rem;
}

.publication-date {
  color: #6B7280;
  font-size: 0.875rem;
}

.publication-category {
  padding: 0.25rem 0.75rem;
  border-radius: 1rem;
  font-size: 0.875rem;
  font-weight: 500;
}

.publication-title {
  color: #1F2937;
  font-size: 1.5rem;
  font-weight: bold;
  margin-bottom: 0.5rem;
  line-height: 1.4;
}

.publication-authors {
  color: #4F46E5;
  font-size: 0.875rem;
  margin-bottom: 1rem;
}

.publication-abstract {
  color: #6B7280;
  font-size: 1rem;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.publication-stats {
  display: flex;
  gap: 2rem;
  margin-bottom: 1.5rem;
}

.stat {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  color: #6B7280;
  font-size: 0.875rem;
}

.stat-icon {
  width: 1.25rem;
  height: 1.25rem;
  color: #4F46E5;
}

.publication-actions {
  display: flex;
  gap: 1rem;
}

.action-button {
  padding: 0.75rem 1.5rem;
  border-radius: 0.75rem;
  font-weight: 500;
  font-size: 0.875rem;
  transition: all 0.2s ease;
  cursor: pointer;
}

.action-button.primary {
  background: #4F46E5;
  color: white;
  border: none;
}

.action-button.primary:hover {
  background: #4338CA;
}

.action-button.secondary {
  background: transparent;
  color: #4F46E5;
  border: 1px solid #4F46E5;
}

.action-button.secondary:hover {
  background: rgba(79, 70, 229, 0.1);
}
</style> 