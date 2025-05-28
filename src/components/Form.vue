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
      <form :class="styles.form">
        <div :class="styles['form-group']">
          <label for="username">Username</label>
          <input id="username" type="text" placeholder="Enter username">
        </div>
        <div :class="styles['form-group']">
          <label for="password">Password</label>
          <input id="password" type="text" placeholder="Enter password">
        </div>
        <div :class="styles['checkbox-wrapper']">
          <input type="checkbox" name="remember-checkbox" id="remember-checkbox">
          <label for="remember-checkbox">Remember me</label>
        </div>
        <button type="submit">Log In</button>
        <div :class="styles['restore-password']">Forgot your password?</div>
      </form>
    </div>
    <footer>
      <div>Don't have an account? <span>Signup now</span></div>
    </footer>
  </div>
</template>

<script setup>
import styles from "./Form.module.css"

defineOptions({
  name: "Form"
})
</script>