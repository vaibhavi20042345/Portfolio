<script setup lang="ts">
import mainImg from '@/assets/mainImg.png'
const title = "Full Stack .NET Developer 🚀 | Angular 🅰️ | React ⚛️ | Vue 🟢 | Web API 🌐 | Mobile App Builder 📱 | AI Learner 🤖"
const desc = "Passionate Full Stack Developer with 8+ years of experience building scalable, enterprise-grade applications. Specializing in ASP.NET Core, Web API, SQL Server, and Angular — with experience in mobile development and a growing focus on AI & Machine Learning. Let's connect and build something amazing together! 🚀"
</script>

<template>
  <section class="hero" id="home">
    <div class="hero-text">
      <p class="greeting">Hi, I'm</p>
      <h1>Vaibhavi Panchal</h1>
      <!-- <h2>Full Stack .NET Developer</h2> -->

      <h3>{{ title }}</h3>
      <p class="desc">{{ desc }}</p>
      <div class="cta">
        <a href="#projects" class="btn-primary">View Projects</a>
        <a href="#contact" class="btn-outline">Contact Me</a>
      </div>
    </div>
    <div class="hero-image">
      <img :src="mainImg" alt="Vaibhavi Panchal" />
    </div>
  </section>
</template>

<style scoped>
.hero {
  display: flex;
  align-items: center;
  justify-content: space-between;
  min-height: calc(100vh - 64px);
  padding: 4rem 6rem;
  background: #0d0d1a;
  gap: 4rem;
}

.hero-text {
  flex: 1;
  max-width: 700px;
}

.greeting {
  font-size: 1.1rem;
  color: #a78bfa;
  margin-bottom: 0.5rem;
  letter-spacing: 0.05em;
}

h1 {
  font-size: 3.5rem;
  font-weight: 800;
  color: #ffffff;
  line-height: 1.1;
  margin-bottom: 0.5rem;
}

h3 {
  font-size: 1.2rem;
  font-weight: 400;
  color: #a78bfa;
  margin-bottom: 1.5rem;
}

.subtitle {
  font-size: 0.95rem;
  color: #c4b5fd;
  margin-bottom: 1rem;
  line-height: 1.6;
}

.desc {
  font-size: 1rem;
  color: #9ca3af;
  line-height: 1.8;
  margin-bottom: 2rem;
}

.cta {
  display: flex;
  gap: 1rem;
}

.btn-primary {
  padding: 0.75rem 1.75rem;
  background: #7c3aed;
  color: #fff;
  border-radius: 8px;
  text-decoration: none;
  font-weight: 600;
  transition: background 0.2s;
}

.btn-primary:hover {
  background: #6d28d9;
}

.btn-outline {
  padding: 0.75rem 1.75rem;
  border: 2px solid #7c3aed;
  color: #a78bfa;
  border-radius: 8px;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.2s;
}

.btn-outline:hover {
  background: #7c3aed;
  color: #fff;
}

.hero-image {
  flex-shrink: 0;
  width: 320px;
  height: 320px;
  border-radius: 50%;
  background: linear-gradient(145deg, #ede9fe, #ddd6fe);
  border: 3px solid rgba(139, 92, 246, 0.3);
  box-shadow: 0 0 40px rgba(139, 92, 246, 0.15);
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
}

.hero-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
}

@media (max-width: 768px) {
  .hero {
    flex-direction: column-reverse;
    padding: 3rem 1.5rem;
    text-align: center;
  }
  h1 { font-size: 2.5rem; }
  .cta { justify-content: center; }
  .hero-image { width: 240px; height: 240px; }
}
</style>
