<script setup>
import { ref } from "vue";

defineProps({
  msg: String,
  name: String,
});

const count = ref(0);
</script>

<template>
  <h1>{{ msg }}</h1>

  <h2>{{ name }}</h2>
</template>
