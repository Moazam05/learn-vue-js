<template>
  <div
    :style="{
      color: 'red',
      fontSize: '20px',
      fontWeight: 'bold',
    }"
  >
    Two Way Data Binding
  </div>
  <br />
  <input type="text" v-model="count" />
  <br />
  <br />
  <div>{{ count }}</div>

  <button @click="hundredHandle">Make Count 100</button>
</template>

<script setup>
import { ref } from "vue";

const count = ref(10);

const hundredHandle = () => {
  count.value = 100;
};
</script>

<script>
export default {
  name: "About",
};
</script>
