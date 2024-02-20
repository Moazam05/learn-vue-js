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
</template>

<script>
export default {
  name: "Home",

  setup() {
    const email = "salmanmoazam08@gmail.com";
    const phone = "1234567890";
    const getName = (name) => {
      return name;
    };

    return { email, phone, getName };
  },

  // data() {
  //   return {
  //     hotMail: "salman@hotmail.com",
  //   };
  // },
};
</script>
