<template>
  <div class="research-page">
    <ResearchHero
      title="Research in AI Medicine"
      description="Exploring the cutting-edge intersection of Artificial Intelligence and Healthcare to revolutionize medical diagnosis, treatment, and patient care."
      :stats="[
        { value: '150+', label: 'Research Projects' },
        { value: '45+', label: 'Partner Institutions' },
        { value: '1000+', label: 'Publications' }
      ]"
    >
      <template #actions>
        <button class="hero-button primary">Join Our Research</button>
        <button class="hero-button secondary">View Publications</button>
      </template>
    </ResearchHero>

    <section class="research-areas">
      <h2 class="section-title">Current Research Areas</h2>
      <div class="research-grid">
        <ResearchCard
          title="Machine Learning in Diagnosis"
          description="Advanced algorithms assisting in medical diagnosis and decision support."
          :items="[
            'Radiology image analysis',
            'Pathology slide interpretation',
            'Clinical decision support systems'
          ]"
        >
          <template #icon>
            <svg class="card-icon" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M21 16V8.00002C20.9996 7.6493 20.9071 7.30483 20.7315 7.00119C20.556 6.69754 20.3037 6.44539 20 6.27002L13 2.27002C12.696 2.09449 12.3511 2.00208 12 2.00208C11.6489 2.00208 11.304 2.09449 11 2.27002L4 6.27002C3.69626 6.44539 3.44398 6.69754 3.26846 7.00119C3.09294 7.30483 3.00036 7.6493 3 8.00002V16C3.00036 16.3508 3.09294 16.6952 3.26846 16.9989C3.44398 17.3025 3.69626 17.5547 4 17.73L11 21.73C11.304 21.9056 11.6489 21.998 12 21.998C12.3511 21.998 12.696 21.9056 13 21.73L20 17.73C20.3037 17.5547 20.556 17.3025 20.7315 16.9989C20.9071 16.6952 20.9996 16.3508 21 16Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </template>
        </ResearchCard>

        <ResearchCard
          title="Natural Language Processing"
          description="Revolutionizing healthcare through advanced text analysis and understanding."
          :items="[
            'Medical literature analysis',
            'Clinical notes interpretation',
            'Patient-doctor communication'
          ]"
        >
          <template #icon>
            <svg class="card-icon" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M21 15C21 15.5304 20.7893 16.0391 20.4142 16.4142C20.0391 16.7893 19.5304 17 19 17H7L3 21V5C3 4.46957 3.21071 3.96086 3.58579 3.58579C3.96086 3.21071 4.46957 3 5 3H19C19.5304 3 20.0391 3.21071 20.4142 3.58579C20.7893 3.96086 21 4.46957 21 5V15Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </template>
        </ResearchCard>

        <ResearchCard
          title="Predictive Analytics"
          description="Using AI to predict disease progression and optimize treatment plans."
          :items="[
            'Disease progression prediction',
            'Patient risk assessment',
            'Treatment outcome forecasting'
          ]"
        >
          <template #icon>
            <svg class="card-icon" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M21 21H3V3" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              <path d="M21 9L13 15L9 11L3 16" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </template>
        </ResearchCard>
      </div>
    </section>

    <section class="latest-publications">
      <h2 class="section-title">Latest Publications</h2>
      <div class="publications-list">
        <PublicationCard
          title="AI-Driven Early Detection of Rare Diseases"
          authors="Dr. Jane Smith, Dr. John Doe, et al."
          abstract="A groundbreaking study on using machine learning algorithms for early detection of rare diseases, showing a 45% improvement in diagnosis time."
          date="2024-02-15"
          category="Machine Learning"
          :citations="128"
          :comments="45"
        />

        <PublicationCard
          title="Natural Language Processing in Clinical Documentation"
          authors="Dr. Michael Johnson, Dr. Sarah Williams"
          abstract="Exploring the implementation of NLP techniques in clinical settings to improve documentation accuracy and efficiency."
          date="2024-02-01"
          category="NLP"
          categoryColor="#059669"
          :citations="89"
          :comments="32"
        />
      </div>
    </section>
  </div>
</template>

<style scoped>
.research-page {
  padding: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

.section-title {
  font-size: 2rem;
  font-weight: 700;
  color: #1F2937;
  margin-bottom: 2rem;
  text-align: center;
}

.research-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-bottom: 4rem;
}

.card-icon {
  width: 100%;
  height: 100%;
}

.publications-list {
  display: flex;
  flex-direction: column;
  gap: 2rem;
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
  .research-page {
    padding: 1rem;
  }

  .research-grid {
    grid-template-columns: 1fr;
  }
}
</style> 