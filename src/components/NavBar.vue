<script setup lang="ts">
const links = [
  { label: 'Home', href: '#home' },
  { label: 'About', href: '#about' },
  { label: 'Education', href: '#education' },
  { label: 'Projects', href: '#projects' },
  { label: 'Contact', href: '#contact' },
]
</script>

<template>
  <nav>
    <span class="brand">Vaibhavi Panchal</span>
    <ul>
      <li v-for="link in links" :key="link.href">
        <a :href="link.href">{{ link.label }}</a>
      </li>
    </ul>
  </nav>
</template>

<style scoped>
nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1rem 6rem;
  background-color: #0d0d1a;
  border-bottom: 1px solid rgba(124, 58, 237, 0.2);
  position: sticky;
  top: 0;
  z-index: 100;
  width: 100%;
}

.brand {
  font-size: 1.2rem;
  font-weight: 700;
  color: #fff;
}

ul {
  display: flex;
  gap: 2rem;
  list-style: none;
  margin: 0;
  padding: 0;
}

a {
  color: #9ca3af;
  text-decoration: none;
  font-size: 0.95rem;
  transition: color 0.2s;
}

a:hover {
  color: #a78bfa;
}
</style>
