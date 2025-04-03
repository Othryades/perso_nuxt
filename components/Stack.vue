<template>
  <section class="text-white stack-section">
    <h2 class="subtitle">stack</h2>
    <div class="stack-grid">
      <div class="tech-item" v-for="tech in technologies" :key="tech">
        {{ tech }}
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      technologies: [
        'HTML',
        'CSS',
        'JavaScript',
        'Vue.js',
        'Nuxt.js',
        'Node.js',
        'GraphQL',
        'Database Management',
        'SQL',
        'PHP',
        'AWS',
        'Docker',
        'CI/CD',
        'Git'
      ]
    }
  }
}
</script>

<style>
.stack-section {
  padding: 2rem;
  max-width: 1200px;
  margin: 0 auto;
  text-align: center;
}

.stack-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
  gap: 0.75rem;
  margin-top: 2rem;
}

.tech-item {
  font-size: 1em;
  font-weight: 500;
  transition: all 0.3s ease;
  cursor: pointer;
  position: relative;
}

.tech-item::after {
  content: '';
  position: absolute;
  bottom: -2px;
  left: 0;
  width: 0;
  height: 2px;
  background-color: var(--color-accent);
  transition: width 0.3s ease;
}

.tech-item:hover {
  color: var(--color-accent);
  transform: translateY(-2px);
}

.tech-item:hover::after {
  width: 100%;
}

@media (max-width: 768px) {
  .tech-item {
    font-size: 0.9em;
  }
}
</style>
