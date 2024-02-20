<template>
  <div
    :style="{
      backgroundColor: 'lightblue',
      padding: '10px',
      margin: '10px',
      borderRadius: '10px',
    }"
  >
    Login Form

    <div :style="{ margin: '20px 0' }">
      <label for="username">Username</label>
      <input type="text" id="username" v-model="formValues.username" />
    </div>

    <div>
      <label for="password">Password</label>
      <input type="password" id="password" v-model="formValues.password" />
    </div>

    <div :style="{ margin: '20px 0' }">
      <button @click="submitHandle">Login</button>
    </div>
  </div>
</template>

<script setup>
import { reactive } from "vue";

const formValues = reactive({
  username: "",
  password: "",
});

const submitHandle = () => {
  console.log("Form submitted");
  const payload = {
    username: formValues.username,
    password: formValues.password,
  };

  console.log("Payload", payload);
};
</script>

<script>
export default {
  name: "Contact",
};
</script>
