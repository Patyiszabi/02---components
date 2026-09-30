<script setup>

import MainNavigation from './components/MainNavigation.vue';
import SiteFooter from './components/SiteFooter.vue';
import SiteContent from './components/SiteContent.vue';
import InputField from './components/InputField.vue';
import { reactive } from 'vue';



const formData = reactive({
  email: '',
  firstName: '',
  lastName: ''
});



function submitForm() {
  console.log('Form submitted:', JSON.stringify(formData));
}

</script>

<template>
  <header>
    <MainNavigation title="My Vue App"/>
  </header>

  <main>
    <SiteContent/>
    <InputField
    v-model="formData.email"
    id="e-mail"
    type="email"
    placeholder="Enter your e-mail"
    label="E-mail address"
     />

    <InputField
    v-model="formData.firstName"
    id="firstname"
    type="text"
    placeholder="Enter your first name"
    label="First name"
     />

    <InputField
    v-model="formData.lastName"
    id="lastname"
    type="text"
    placeholder="Enter your last name"
    label="Last name"
     />

     <button @click="submitForm">Submit</button>

  </main>

  <footer>
    <SiteFooter />
  </footer>

</template>

<style scoped></style>
