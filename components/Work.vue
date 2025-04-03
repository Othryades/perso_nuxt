<template>
  <section class="work-section">
    <h2 class="subtitle text-white">work</h2>
    <div class="work-timeline">
      <div class="work-item" v-for="job in jobs" :key="job.company">
        <div class="work-date">{{ job.period }}</div>
        <div class="work-content">
          <h3 class="work-title">{{ job.title }}</h3>
          <h4 class="work-company">{{ job.company }}</h4>
          <p class="work-description">{{ job.description }}</p>
          <div class="work-tags">
            <span v-for="tag in job.tags" :key="tag" class="tag">{{ tag }}</span>
          </div>
          <a v-if="job.link" :href="job.link" target="_blank" class="work-link">
            View Project
            <svg class="arrow-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
              <path d="M5 12h14M12 5l7 7-7 7"/>
            </svg>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      jobs: [
        {
          period: '2024 - Present',
          title: 'Senior Technical Support Engineer',
          company: 'Consensys',
          description: 'Working on Web3 applications and blockchain development, specifaclly on Linea zkEVM Layer 2.',
          tags: ['DeFi', 'Web3', 'Blockchain', 'TypeScript'],
          link: 'https://consensys.io'
        },
        {
          period: '2022 - 2024',
          title: 'Technical Support Engineer',
          company: 'Bloxroute',
          description: 'Development of blockchain infrastructure and Web3 applications.',
          tags: ['MEV', 'Web3', 'Blockchain', 'DeFi'],
          link: 'https://bloxroute.com'
        },
        {
          period: '2019 - 2022',
          title: 'Full Stack Developer',
          company: 'Groupe TRAVELFACTORY',
          description: 'Development of travel and leisure applications.',
          tags: ['Vue.js', 'Ajax', 'API', 'ES6', 'Agile'],
          link: 'https://travelfactory.com'
        },
        {
          period: '2018 - 2019',
          title: 'Full Stack Developer',
          company: 'Moonshot Marketing LTD',
          description: 'Development of landing pages and ecommerce websites using serverless Google Firebase.',
          tags: ['React', 'Firebase', 'Bootstrap', 'E-commerce'],
          link: 'https://www.moonshot-marketing.com'
        },
        {
          period: '2017 - 2018',
          title: 'Full Stack Developer',
          company: 'Wise Group Media Ltd',
          description: 'Development of responsive funnels and websites using Bootstrap 4 and PHP.',
          tags: ['PHP', 'JavaScript', 'Bootstrap', 'Responsive Design'],
          link: 'https://www.clearex.co.il'
        },
        {
          period: '2017 - 2018',
          title: 'Full Stack Developer',
          company: 'Freelance, Self employed',
          description: 'Development of an open source marketing funnel analysis platform (LAMP).',
          tags: ['PHP', 'MySQL', 'JavaScript', 'LAMP Stack']
        }
      ]
    }
  }
}
</script>

<style>
.work-section {
  padding: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

.work-timeline {
  position: relative;
  margin-top: 2rem;
}

.work-timeline::before {
  content: '';
  position: absolute;
  left: 0;
  top: 0;
  height: 100%;
  width: 2px;
  background: var(--color-accent);
  opacity: 0.3;
}

.work-item {
  position: relative;
  padding-left: 2rem;
  margin-bottom: 3rem;
}

.work-item::before {
  content: '';
  position: absolute;
  left: 0;
  top: 0.5rem;
  width: 1rem;
  height: 1rem;
  border-radius: 50%;
  background: var(--color-accent);
  border: 2px solid var(--color-bg);
}

.work-date {
  font-size: 0.9em;
  color: var(--color-accent);
  margin-bottom: 0.5rem;
}

.work-content {
  background: var(--color-surface);
  padding: 1.5rem;
  border-radius: 0.5rem;
  transition: transform 0.3s ease;
}

.work-content:hover {
  transform: translateY(-2px);
}

.work-title {
  font-size: 1.25em;
  font-weight: 600;
  color: var(--color-text);
  margin-bottom: 0.25rem;
}

.work-company {
  font-size: 1.1em;
  color: var(--color-accent);
  margin-bottom: 0.75rem;
}

.work-description {
  color: var(--color-text);
  opacity: 0.8;
  margin-bottom: 1rem;
  line-height: 1.6;
}

.work-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-bottom: 1rem;
}

.tag {
  font-size: 0.85em;
  padding: 0.25rem 0.75rem;
  background: var(--color-accent);
  color: var(--color-bg);
  border-radius: 1rem;
  opacity: 0.9;
  font-weight: 400;
}

.work-link {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  color: var(--color-accent);
  text-decoration: none;
  font-size: 0.9em;
  transition: gap 0.3s ease;
}

.work-link:hover {
  gap: 0.75rem;
}

.arrow-icon {
  width: 1em;
  height: 1em;
}

@media (max-width: 768px) {
  .work-section {
    padding: 1rem;
  }

  .work-item {
    padding-left: 1.5rem;
    margin-bottom: 2rem;
  }

  .work-content {
    padding: 1rem;
  }

  .work-title {
    font-size: 1.1em;
  }

  .work-company {
    font-size: 1em;
  }

  .work-description {
    font-size: 0.9em;
  }
}
</style>
