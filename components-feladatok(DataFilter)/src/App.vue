<script setup>
import MainNavigation from './components/MainNavigation.vue'
import DataFilter from './components/DataFilter.vue'
import SiteFooter from './components/SiteFooter.vue'
</script>

<template>
  <header>
    <MainNavigation />
  </header>

  <main>
    <DataFilter />
  </main>

  <SiteFooter />
</template>

<style scoped></style>
