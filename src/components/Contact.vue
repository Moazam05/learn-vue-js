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

    <!-- checkbox -->
    <div>
      <input
        type="checkbox"
        id="vehicle1"
        name="vehicle1"
        v-model="vehicles.bike"
        value="Bike"
      />
      <label for="vehicle1"> I have a bike</label><br />

      <input
        type="checkbox"
        id="vehicle2"
        name="vehicle2"
        v-model="vehicles.car"
        value="Car"
      />
      <label for="vehicle2"> I have a car</label><br />

      <input
        type="checkbox"
        id="vehicle3"
        name="vehicle3"
        v-model="vehicles.boat"
        value="Boat"
      />
      <label for="vehicle3"> I have a boat</label><br />
    </div>

    <div>
      <label for="male">Male</label>

      <input
        type="radio"
        name="gender"
        value="male"
        v-model="formValues.gender"
        id="male"
      />
      <label for="female">Female</label>

      <input
        type="radio"
        name="gender"
        v-model="formValues.gender"
        value="female"
        id="male"
      />
    </div>
  </div>
</template>

<script setup>
import { reactive } from "vue";

const formValues = reactive({
  username: "",
  password: "",
  gender: null,
});

const vehicles = reactive({
  bike: false,
  car: false,
  boat: false,
});

const submitHandle = () => {
  console.log("Form submitted");
  const payload = {
    username: formValues.username,
    password: formValues.password,
    gender: formValues.gender,
  };

  console.log("Payload", payload, vehicles);
};
</script>

<script>
export default {
  name: "Contact",
};
</script>
