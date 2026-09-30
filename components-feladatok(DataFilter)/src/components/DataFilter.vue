<script setup>
import { ref, computed, watch } from 'vue'

const data = [
  { id: 1, name: 'John Doe' },
  { id: 2, name: 'Jane Doe' },
  { id: 3, name: 'Jim Smith' },
  { id: 4, name: 'Sarah Johnson' },
]

const search = ref('')

const filteredData = computed(() =>
  data.filter((item) => item.name.toLowerCase().includes(search.value.toLowerCase())),
)

watch(search, (newValue) => {
  console.log(newValue)
})
</script>

<template>
  <div class="data-filter">
    <input v-model="search" type="text" placeholder="Search by name..." />
    <ul>
      <li v-for="item in filteredData" :key="item.id">{{ item.name }}</li>
    </ul>
    <p v-if="filteredData.length === 0" class="empty">No matching names.</p>
  </div>
</template>

<style scoped>
.data-filter {
  max-width: 400px;
  margin: 2rem auto;
}

input {
  width: 100%;
  padding: 0.6rem 0.8rem;
  border: 1px solid #ccc;
  border-radius: 6px;
  font-size: 1rem;
}

ul {
  margin: 1rem 0 0;
  padding: 0;
  list-style: none;
}

li {
  padding: 0.5rem 0.8rem;
  border-bottom: 1px solid #eee;
}

.empty {
  margin-top: 1rem;
  color: #888;
}
</style>
