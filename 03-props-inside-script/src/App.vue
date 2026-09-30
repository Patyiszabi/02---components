<script setup>

import MainNavigation from './components/MainNavigation.vue';
import SiteFooter from './components/SiteFooter.vue';
import SiteContent from './components/SiteContent.vue';
import InputField from './components/InputField.vue';

import { ref } from 'vue';

const title = ref('My Vue App');

setTimeout(() => {
  title.value = 'My Vue App - Updated Title';
}, 3000);


const name = ref('');

function logMessage() {
  console.log(name);
}

</script>

<template>
  <header>
    <MainNavigation :title="title" />
  </header>

  <main>
    <SiteContent />
    <InputField @on-input="logMessage" />
  </main>

  <footer>
    <SiteFooter />
  </footer>

</template>

<style scoped></style>
