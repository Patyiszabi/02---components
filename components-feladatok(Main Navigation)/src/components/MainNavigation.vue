<script setup>
const menu = [
  {
    text: 'Vue.js',
    url: 'https://vuejs.org/',
  },
  {
    text: 'React',
    url: 'https://reactjs.org/',
  },
  {
    text: 'Angular',
    url: 'https://angular.io/',
  },
  {
    text: 'Svelte',
    url: 'https://svelte.dev/',
  },
]
</script>

<template>
  <nav class="main-nav">
    <span class="brand">Frameworks</span>
    <ul>
      <li v-for="item in menu" :key="item.url">
        <a :href="item.url" target="_blank" rel="noopener">{{ item.text }}</a>
      </li>
    </ul>
  </nav>
</template>

<style scoped>
.main-nav {
  position: sticky;
  top: 0;
  z-index: 10;
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 0.5rem;
  width: 100%;
  padding: 0.75rem 2rem;
  background: linear-gradient(90deg, #2c3e50, #35495e);
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.25);
}

.brand {
  color: #42b883;
  font-size: 1.25rem;
  font-weight: 700;
  letter-spacing: 0.03em;
}

ul {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin: 0;
  padding: 0;
  list-style: none;
}

a {
  display: block;
  padding: 0.5rem 1rem;
  border-radius: 6px;
  color: #ecf0f1;
  font-weight: 500;
  text-decoration: none;
  transition:
    background-color 0.2s,
    color 0.2s;
}

a:hover,
a:focus-visible {
  background-color: #42b883;
  color: #fff;
}
</style>
