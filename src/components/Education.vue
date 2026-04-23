<script setup lang="ts">
const education = [
  { year: '2021–2022', degree: 'Postgraduate Degree in Network Architecture and Security Analyst', school: 'Sault College, Canada' },
  { year: '2020–2021', degree: 'Postgraduate Degree in Mobile Applications Design', school: 'Sault College, Canada' },
  { year: '2013–2015', degree: "Master's in Computer Engineering", school: 'Gujarat Technological University, India' },
  { year: '2008–2012', degree: "Bachelor's in Computer Engineering", school: 'Gujarat Technological University, India' },
]

const certificates = [
  { name: 'Certificate of completion: Claude 101', issuer: 'Anthropic', date: 'Arp 2026', link:'https://verify.skilljar.com/c/2cwmopv3qc96' },
  { name: 'Microsoft Azure Cosmos DB', issuer: 'Microsoft', date: 'Jan 2026' , link:'https://www.coursera.org/account/accomplishments/verify/SN4AM7NJYMIR' },
  { name: 'AWS Introduction to Generative AI – Art of the Possible', issuer: 'Amazon Web Services (AWS)', date: 'Sep 2025', link:'https://www.linkedin.com/in/vaibhavi0490/overlay/Certifications/1491127015/treasury?profileId=ACoAAC-DUQ4BdT0wpMDsGcX_8ATOJ0-qLrVtLVI'},
  { name: 'Foundational C# with Microsoft', issuer: 'freeCodeCamp', date: 'Mar 2025', link:'https://www.freecodecamp.org/certification/fcc74564a36-34ed-4436-b034-59406e262735/foundational-c-sharp-with-microsoft' },
  { name: 'Angular Essential Training', issuer: 'LinkedIn Learning', date: 'Aug 2024', link:'https://www.linkedin.com/learning/certificates/a4f13cc493854c59103a5e771001c8eed4fb37779f552fea66e47040581d588c?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_certifications_details%3BRARZcV2aTAmasliyDFQ%2B%2BA%3D%3D' },
  { name: 'The Non-Technical Skills of Effective Data Scientists', issuer: 'LinkedIn Learning', date: 'Jul 2024', link:'https://www.linkedin.com/learning/certificates/25c2b345721b172735a7daaf91c73d547f32e204d80806a45208317ece36efe3?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_certifications_details%3BRARZcV2aTAmasliyDFQ%2B%2BA%3D%3D' },
  { name: 'Programming Foundations: Data Structures', issuer: 'LinkedIn Learning', date: 'Aug 2022', link:'https://www.linkedin.com/learning/certificates/272865c7e2333b3728a0441bf8a56575ddc96cc693109a2dfdd9bbee97025491?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_certifications_details%3BRARZcV2aTAmasliyDFQ%2B%2BA%3D%3D' },
]
</script>

<template>
  <section class="education" id="education">
    <div class="edu-grid">

      <!-- Left: Education Timeline -->
      <div class="edu-left">
        <h2 class="section-title"><span class="icon">🎓</span> Education</h2>
        <div class="timeline">
          <div class="timeline-item" v-for="item in education" :key="item.year">
            <div class="timeline-year">{{ item.year }}</div>
            
            <div class="timeline-content">
              <p class="degree">{{ item.degree }}</p>
              <p class="school">{{ item.school }}</p>
            </div>
          </div>
        </div>
      </div>

      <!-- Right: Certificates -->
      <div class="edu-right">
        <h2 class="section-title"><span class="icon">📜</span> Certificates</h2>
        <ul class="cert-list">
          <li v-for="cert in certificates" :key="cert.name">
            <div class="cert-row">
              <span class="cert-name">{{ cert.name }}</span>
              <a :href="cert.link" target="_blank" rel="noopener noreferrer" class="cert-btn">View ↗</a>
            </div>
            <span class="cert-meta">{{ cert.issuer }} · {{ cert.date }}</span>
          </li>
        </ul>
      </div>

    </div>
  </section>
</template>

<style scoped>
.education {
  background: #0d0d1a;
  padding: 5rem 6rem;
}

.edu-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
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

/* Timeline */
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
  min-width: 5.5rem;
  font-size: 0.82rem;
  font-weight: 700;
  color: #a78bfa;
  padding-top: 0.15rem;
  text-align: right;
  flex-shrink: 0;
}

/* .timeline-dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: #7c3aed;
  border: 2px solid #a78bfa;
  flex-shrink: 0;
  margin-top: 0.3rem;
} */

.timeline-content {
  border-left: 2px solid #7c3aed;
  padding-left: 1rem;
}

.degree {
  font-size: 1rem;
  font-weight: 600;
  color: #ffffff;
}

.school {
  font-size: 0.9rem;
  color: #9ca3af;
}

/* Certificates */
.cert-list {
  list-style: disc;
  padding-left: 1.25rem;
  display: flex;
  flex-direction: column;
  gap: 0.9rem;
}

.cert-list li {
  color: #d1d5db;
  font-size: 0.95rem;
  line-height: 1.5;
  display: flex;
  flex-direction: column;
  gap: 0.15rem;
}

.cert-row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 0.5rem;
}

.cert-name {
  color: #ffffff;
  font-weight: 500;
}

.cert-btn {
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

.cert-btn:hover {
  background: #7c3aed;
  color: #fff;
}

.cert-meta {
  font-size: 0.82rem;
  color: #a78bfa;
}

.cert-list li::marker {
  color: #7c3aed;
}

@media (max-width: 768px) {
  .education {
    padding: 3rem 1.25rem;
  }
  .edu-grid {
    grid-template-columns: 1fr;
    gap: 2.5rem;
  }
  .timeline-year {
    min-width: 4.5rem;
    font-size: 0.75rem;
  }
  .cert-row {
    flex-wrap: wrap;
    gap: 0.4rem;
  }
  .cert-btn {
    font-size: 0.7rem;
  }
}
</style>
