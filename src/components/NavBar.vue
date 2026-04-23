<script setup lang="ts">
import { ref } from 'vue'
const links = [
  { label: 'Home', href: '#home' },
  { label: 'About', href: '#about' },
  { label: 'Education', href: '#education' },
  { label: 'Projects', href: '#projects' },
  { label: 'Contact', href: '#contact' },
]
const menuOpen = ref(false)
function closeMenu() { menuOpen.value = false }
</script>

<template>
  <nav>
    <span class="brand">Vaibhavi Panchal</span>
    <button class="hamburger" @click="menuOpen = !menuOpen" aria-label="Toggle menu">
      <span></span><span></span><span></span>
    </button>
    <ul :class="{ open: menuOpen }">
      <li v-for="link in links" :key="link.href">
        <a :href="link.href" @click="closeMenu">{{ link.label }}</a>
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
  box-sizing: border-box;
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

a:hover { color: #a78bfa; }

.hamburger {
  display: none;
  flex-direction: column;
  gap: 5px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 4px;
}

.hamburger span {
  display: block;
  width: 24px;
  height: 2px;
  background: #fff;
  border-radius: 2px;
}

@media (max-width: 768px) {
  nav { padding: 1rem 1.5rem; }

  .hamburger { display: flex; }

  ul {
    display: none;
    flex-direction: column;
    gap: 0;
    position: absolute;
    top: 100%;
    left: 0;
    width: 100%;
    background: #0d0d1a;
    border-top: 1px solid rgba(124, 58, 237, 0.2);
    padding: 0.5rem 0;
  }

  ul.open { display: flex; }

  ul li a {
    display: block;
    padding: 0.75rem 1.5rem;
    font-size: 1rem;
  }
}
</style>
