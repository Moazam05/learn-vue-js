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
      <li v-for="user in users" :key="user.id">
        {{ user.name }}
        <button @click="showName(user?.name)">Show Name</button>
      </li>
    </ul>
  </div>
</template>

<script setup>
defineProps({
  users: Array,
});

const showName = (name) => {
  alert(name);
};
</script>

<script>
export default {
  name: "User",
};
</script>
