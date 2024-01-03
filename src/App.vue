<script setup>

import { ref } from 'vue';

function generatePassword(length) {
  const characters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789!@#$%^&*()_+{}[]|;:,.<>?';
  let password = '';

  for (let i = 0; i < length; i++) {
    const randomIndex = Math.floor(Math.random() * characters.length);
    password += characters.charAt(randomIndex);
  }
  return password;
}
const password = ref('');
function generateAndSetPassword() {
  password.value = generatePassword(12);
}

</script>

<template>
  <div>
    <div class="header">
      <h1>ЗДЕСЬ ВЫ МОЖЕТЕ СГЕНЕРИРОВАТЬ СЕБЕ НАДЕЖНЫЙ ПАРОЛЬ</h1>
      <img src="/assets/passw.svg" class="logo" alt="generate" />
    </div>
    <button class="generate" @click="generateAndSetPassword">СГЕНЕРИРОВАТЬ ПАРОЛЬ</button>
    <div class="password-input">
      <input type="text" v-model="password" readonly>
    </div>
  </div>
</template>

<style scoped>
.header h1{
  font-size: 26pt;
  font-weight: 400;
  margin-bottom: 50px;
}
.generate {
  height: 200px;
  width: 500px;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
  font-size: 22pt;
  margin-bottom: 50px;
  margin-top: 100px;
}

.logo img{
  width: 250px;
  height: auto;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
.generate:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.generate.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
.generate-button {
  height: 50px;
  font-size: 16pt;
  margin-bottom: 20px;
  cursor: pointer;
}

input {
  width: 400px;
  height: 200px;
  box-sizing: border-box;
  border: 5px #0d97f3;
  border-radius: 20px;
  text-align: center;
  align-items: center;
  font-size: 26pt;
}

input:focus {
  border-color: #3498db;
}

input:hover {
  border-color: #3498db;
}
</style>

