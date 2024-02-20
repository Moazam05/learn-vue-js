<template>
  <div :style="{ color: 'red', fontSize: '20px', fontWeight: 'bold' }">
    For Loop
  </div>

  <div>
    <ul>
      <li v-for="item in technologies" :key="item">{{ item }}</li>
    </ul>

    <div>
      <ul>
        <li v-for="user in users" :key="user.id">{{ user.name }}</li>
      </ul>
    </div>
  </div>
</template>

<script setup>
const technologies = ["Vue", "React", "Angular", "Svelte", "Ember"];

const users = [
  { id: 1, name: "Salman" },
  { id: 2, name: "Ali" },
  { id: 3, name: "Ahmed" },
  { id: 4, name: "Kashif" },
  { id: 5, name: "Nasir" },
];
</script>

<script>
export default {
  name: "Dashboard",
};
</script>
