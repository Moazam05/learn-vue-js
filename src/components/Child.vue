<template>
  <div :style="{ color: 'red', fontSize: '20px', fontWeight: 'bold' }">
    Child Component
  </div>

  <div>{{ name }}</div>
  <div>{{ userDetails.name }}</div>
  <div>{{ userDetails.age }}</div>
  <div>{{ userDetails.email }}</div>

  <div>{{ currentDate() }}</div>
</template>

<script setup>
defineProps({
  name: String,
  userDetails: Object,
  currentDate: Function,
});
</script>

<script>
export default {
  name: "Child",
};
</script>
