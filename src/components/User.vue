<template>
  <div
    :style="{
      color: 'red',
      fontSize: '20px',
      fontWeight: 'bold',
    }"
  >
    User Component
  </div>

  <div>
    <ul>
      <li
        v-for="user in users"
        :key="user.id"
        :style="{
          color: currentUser?.value?.id === user.id ? 'red' : 'green',
        }"
      >
        {{ user.name }}
        <button @click="showName(user)">Show Name</button>
      </li>
    </ul>
  </div>
</template>

<script setup>
// Imports
import { reactive } from "vue";

// Props
defineProps({
  users: Array,
});

// States
const currentUser = reactive({
  value: null,
});

const showName = (user) => {
  currentUser.value = user;
};
</script>

<script>
export default {
  name: "User",
};
</script>
