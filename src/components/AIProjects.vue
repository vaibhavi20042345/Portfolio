<script setup lang="ts">
const projects = [
  {
    name: 'Claude Chat API (.NET + Anthropic)',
    description: 'AI-powered chat API built with ASP.NET Core and Anthropic Claude. Features clean service-layer architecture, structured DTOs, error handling, and Swagger support.',
    stack: ['ASP.NET Core', 'C#', 'Anthropic Claude API', 'Swagger'],
    link: 'https://github.com/vaibhavi20042345/ClaudeChatApi'
  }
]
</script>

<template>
  <section class="aiprojects" id="aiprojects">
    <h2 class="section-title"><span class="icon">🤖</span> AI Projects</h2>
    <div class="projects-grid">
      <div class="project-card" v-for="project in projects" :key="project.name">
        <div class="card-header">
          <p class="project-name">{{ project.name }}</p>
          <a :href="project.link" target="_blank" rel="noopener noreferrer" class="github-btn">GitHub ↗</a>
        </div>
        <p class="project-desc">{{ project.description }}</p>
        <div class="stack-tags">
          <span class="tag" v-for="tech in project.stack" :key="tech">{{ tech }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.aiprojects {
  background: #0d0d1a;
  padding: 5rem 6rem;
}

.section-title {
  font-size: 1.6rem;
  font-weight: 700;
  color: #ffffff;
  margin-bottom: 2rem;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.icon {
  font-size: 1.5rem;
}

.projects-grid {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.project-card {
  border-left: 2px solid #7c3aed;
  padding-left: 1rem;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.card-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 0.5rem;
}

.project-name {
  font-size: 1rem;
  font-weight: 600;
  color: #ffffff;
}

.github-btn {
  font-size: 0.75rem;
  padding: 0.2rem 0.6rem;
  border: 1px solid #7c3aed;
  border-radius: 4px;
  color: #a78bfa;
  text-decoration: none;
  white-space: nowrap;
  flex-shrink: 0;
  transition: background 0.2s, color 0.2s;
}

.github-btn:hover {
  background: #7c3aed;
  color: #fff;
}

.project-desc {
  font-size: 0.9rem;
  color: #9ca3af;
  line-height: 1.5;
}

.stack-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.4rem;
}

.tag {
  font-size: 0.75rem;
  padding: 0.15rem 0.5rem;
  background: #1a1a2e;
  border: 1px solid #7c3aed;
  border-radius: 4px;
  color: #a78bfa;
}

@media (max-width: 768px) {
  .aiprojects {
    padding: 3rem 1.25rem;
  }
  .card-header {
    flex-wrap: wrap;
  }
}
</style>