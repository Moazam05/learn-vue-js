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

  <div>
    <!-- Use a function call directly -->
    <button @click="childFunc('Salman')">Child Data</button>
  </div>
</template>

<script setup>
// Imports
import { reactive } from "vue";

// Props
defineProps({
  users: Array,
  childFunc: Function,
});

// States
const currentUser = reactive({
  value: null,
});

// Methods
const showName = (user) => {
  alert(user.name);
  currentUser.value = user;
};
</script>

<script>
export default {
  name: "User",
};
</script>
