<script setup lang="ts">
import mainImg from '@/assets/mainImg.png'
const desc = "Passionate Full Stack Developer with 8+ years of experience building scalable, enterprise-grade applications. Specializing in ASP.NET Core, Web API, SQL Server, and Angular — with experience in mobile development and a growing focus on AI & Machine Learning."
</script>

<template>
  <section class="hero" id="home">
    <div class="hero-text">
      <p class="greeting">Hi, I'm</p>
      <h1>Vaibhavi Panchal</h1>
      <h2>Full Stack .NET Developer</h2>
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
  max-width: 600px;
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

h2 {
  font-size: 1.5rem;
  font-weight: 500;
  color: #a78bfa;
  margin-bottom: 1.5rem;
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
}

.hero-image img {
  width: 320px;
  height: 320px;
  object-fit: cover;
  border-radius: 50%;
  border: 4px solid #7c3aed;
  box-shadow: 0 0 40px rgba(124, 58, 237, 0.5);
}

@media (max-width: 768px) {
  .hero {
    flex-direction: column-reverse;
    padding: 3rem 1.5rem;
    text-align: center;
  }
  h1 { font-size: 2.5rem; }
  .cta { justify-content: center; }
  .hero-image img { width: 220px; height: 220px; }
}
</style>
