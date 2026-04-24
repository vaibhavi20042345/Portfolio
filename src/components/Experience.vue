<script setup lang="ts">
const experience = [
  { period: 'Sep 2024–Present', role: 'Software Engineer', company: 'RBH Access Technologies Inc., Ontario, Canada' },
  { period: 'Mar 2023–Jun 2024', role: 'Software Developer', company: 'RBC, Toronto, ON' },
  { period: 'May 2022–Aug 2022', role: 'eLearning Developer (Full-time)', company: 'Sault College, Sault Ste. Marie, ON' },
  { period: 'Oct 2021–Apr 2022', role: 'eLearning Developer (Part-time)', company: 'Sault College, Sault Ste. Marie, ON' },
  // { period: 'Jun 2020–Jan 2021', role: 'Software Developer', company: 'Rigel Networks Private Ltd., India' },
  { period: 'Dec 2017–Nov 2019', role: 'Software Developer', company: 'Civica Resource Private Ltd., India' },
  { period: 'Jul 2015–Nov 2017', role: 'Software Developer', company: 'Yukon Technologies PVT Ltd., India' },
]
</script>

<template>
  <section class="experience" id="experience">
    <h2 class="section-title"><span class="icon">💼</span> Experience</h2>
    <div class="timeline">
      <div class="timeline-item" v-for="item in experience" :key="item.period">
        <div class="timeline-year">{{ item.period }}</div>
        <div class="timeline-content">
          <p class="role">{{ item.role }}</p>
          <p class="company">{{ item.company }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.experience {
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

.timeline {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.timeline-item {
  display: flex;
  align-items: flex-start;
  gap: 1rem;
}

.timeline-year {
  min-width: 9rem;
  font-size: 0.82rem;
  font-weight: 700;
  color: #a78bfa;
  padding-top: 0.15rem;
  text-align: right;
  flex-shrink: 0;
}

.timeline-content {
  border-left: 2px solid #7c3aed;
  padding-left: 1rem;
}

.role {
  font-size: 1rem;
  font-weight: 600;
  color: #ffffff;
}

.company {
  font-size: 0.9rem;
  color: #9ca3af;
}

@media (max-width: 768px) {
  .experience {
    padding: 3rem 1.25rem;
  }
  .timeline-year {
    min-width: 6rem;
    font-size: 0.75rem;
  }
}
</style>