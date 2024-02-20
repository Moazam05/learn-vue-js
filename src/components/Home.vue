<template>
  <div
    :style="{
      color: 'red',
      fontSize: '20px',
      fontWeight: 'bold',
    }"
  >
    Home Page
  </div>
  <div>Email: {{ email }}</div>
  <div>Phone: {{ phone }}</div>
  <div>Name: {{ getName("Salman") }}</div>
  <div>Name: {{ getName("Kashif") }}</div>
  <!-- <div>HotMail: {{ hotMail }}</div> -->
  <button @click="clickMe">Click ME</button>
  <div>Current Date: {{ getDate() }}</div>
  <button @click="handleIncrement">++</button>
  <div>Count: {{ count }}</div>
  <button @click="handleDecrement" :disabled="count === 0">--</button>
</template>

<script setup>
import { ref } from "vue";

const email = "salmanmoazam08@gmail.com";
const phone = "1234567890";
const count = ref(0);

const getName = (name) => {
  return name;
};

const clickMe = () => {
  alert("Hello World");
};

const handleIncrement = () => {
  count.value++;
};

const handleDecrement = () => {
  count.value--;
};

const getDate = () => {
  return new Date().toLocaleDateString();
};
</script>

<script>
export default {
  name: "Home",
};
</script>
