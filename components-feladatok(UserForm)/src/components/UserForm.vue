<script setup>
import { reactive, computed } from 'vue'

const initialState = {
  username: '',
  password: '',
  confirmPassword: '',
}

const form = reactive({ ...initialState })

const usernameError = computed(
  () => form.username.length < 5 || form.username === form.password,
)

const passwordError = computed(
  () => form.password.length < 8 || form.password === form.username,
)

const confirmPasswordError = computed(
  () => form.confirmPassword.length < 8 || form.confirmPassword !== form.password,
)

function submitForm() {
  if (usernameError.value || passwordError.value || confirmPasswordError.value) {
    return
  }

  alert(
    `Username: ${form.username}\nPassword: ${form.password}\nConfirm password: ${form.confirmPassword}`,
  )

  Object.assign(form, initialState)
}
</script>

<template>
  <form class="user-form" @submit.prevent="submitForm">
    <div class="field">
      <label for="username">Username</label>
      <input id="username" v-model="form.username" name="username" type="text" />
      <p v-if="usernameError" class="error">
        Username must be at least 5 characters long and different from password
      </p>
    </div>

    <div class="field">
      <label for="password">Password</label>
      <input id="password" v-model="form.password" name="password" type="password" />
      <p v-if="passwordError" class="error">
        Password must be at least 8 characters long and different from username
      </p>
    </div>

    <div class="field">
      <label for="confirmPassword">Confirm password</label>
      <input
        id="confirmPassword"
        v-model="form.confirmPassword"
        name="confirmPassword"
        type="password"
      />
      <p v-if="confirmPasswordError" class="error">
        Confirm password must be at least 8 characters long and match with password
      </p>
    </div>

    <button type="submit">Küldés</button>
  </form>
</template>

<style scoped>
.user-form {
  max-width: 400px;
  margin: 2rem auto;
}

.field {
  margin-bottom: 1rem;
}

label {
  display: block;
  margin-bottom: 0.3rem;
  font-weight: 600;
}

input {
  width: 100%;
  padding: 0.6rem 0.8rem;
  border: 1px solid #ccc;
  border-radius: 6px;
  font-size: 1rem;
}

.error {
  margin-top: 0.3rem;
  color: #d93025;
  font-size: 0.9rem;
}

button {
  padding: 0.6rem 1.5rem;
  border: none;
  border-radius: 6px;
  background-color: #42b883;
  color: #fff;
  font-size: 1rem;
  cursor: pointer;
}

button:hover {
  background-color: #369870;
}
</style>
