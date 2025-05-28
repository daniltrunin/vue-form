<template>
  <div :class="styles.container">
    <div :class="styles.header">
      <div :class="styles['header-wrapper']">
        <div :class="styles.heading">Welcome Back!</div>
        <div>Sign in to continue</div>
      </div>
      <div>
        <img src="../../public/header_image.png" alt="Header image">
      </div>
    </div>
    <div :class="styles.main">
      <img :class="styles.pfp" src="../../public/profile-picture.jpg" alt="Profile picture">
      <form @submit="handleSubmit" :class="styles.form">
        <div :class="styles['form-group']">
          <label for="username">Username</label>
          <input id="username" type="text" placeholder="Enter username" v-model="username">
        </div>
        <div :class="styles['form-group']">
          <label for="password">Password</label>
          <input id="password" type="text" placeholder="Enter password" v-model="password">
        </div>
        <div :class="styles['checkbox-wrapper']">
          <input type="checkbox" name="remember-checkbox" id="remember-checkbox" v-model="isRemember">
          <label for="remember-checkbox">Remember me</label>
        </div>
        <button type="submit">Log In</button>
        <div @click="(e) => handleReset(e)" :class="styles['restore-password']">Forgot your password?</div>
      </form>
    </div>
    <footer>
      <div>Don't have an account? <span @click="(e) => handleRegister(e)">Signup now</span></div>
    </footer>
  </div>
</template>

<script setup>
import { ref } from "vue";

const username = ref('');
const password = ref('');
const isRemember = ref('');

function handleSubmit(e) {
  e.preventDefault();

  if (username.value == '' || password.value == '') {
    alert('Заполните все поля')
    return
  }

  console.log({
    username: username.value,
    password: password.value,
    isRemember: isRemember.value
  });

  username.value = "";
  password.value = "";
  isRemember.value = false;
}

function handleRegister(e) {
  console.log('Нажата кнопка регистрации: ', e.target.textContent)
}

function handleReset(e) {
  console.log("Нажата кнопка восстановления пароля: ", e.target.textContent)
}

import styles from "./Form.module.css"

defineOptions({
  name: "Form"
})
</script>