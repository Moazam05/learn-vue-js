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

  <div>
    <Child
      name="Salman"
      :userDetails="userDetails"
      :currentDate="currentDate"
    />
  </div>

  <div
    :style="{
      margin: '20px 0',
    }"
  >
    <User :users="users" :childFunc="childFunc" />
  </div>

  <div>Data passing from child to parent:{{ childName?.name }}</div>
</template>

<script setup>
import { reactive } from "vue";
import Child from "./Child.vue";
import User from "./User.vue";

const userDetails = {
  name: "Salman",
  age: 25,
  email: "salmanmoazam08@gmail.com",
};

const technologies = ["Vue", "React", "Angular", "Svelte", "Ember"];

const currentDate = () => {
  const date = new Date();
  return `${date.getDate()}-${date.getMonth() + 1}-${date.getFullYear()}`;
};

const users = [
  { id: 1, name: "Salman" },
  { id: 2, name: "Ali" },
  { id: 3, name: "Ahmed" },
  { id: 4, name: "Kashif" },
];

const childName = reactive({
  name: "",
});

let dataFromChild = "";
const childFunc = (name) => {
  dataFromChild = name;
  childName.name = name;
  console.log("Data from child", name);
};
</script>

<script>
export default {
  name: "Dashboard",
};
</script>
