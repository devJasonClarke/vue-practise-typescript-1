<template>
  <div class="home">
    {{ num }}

    {{ jason }}

    {{ user }}

    {{ items }}

    <button @click="increment">increment</button>

    {{ firstName }}
    {{ lastName }}
    {{ fullName }}
    {{ car }}

    <form @submit.prevent="generateFullName(firstName, lastName)">
      <input type="text" v-model="firstName" />
      <input type="text" v-model="lastName" />
      <button type="submit">submit</button>
    </form>
  </div>
</template>

<script setup lang="ts">
// import { Options, Vue } from 'vue-class-component';

import { ref } from "@vue/reactivity";

const firstName = ref("");
const lastName = ref("");
const fullName = ref("");
const num = ref(1);

let jason: string;
interface users {
  name: string;
  id: number;
}

jason = "hi how are you";

let user: users = {
  name: "Jason",
  id: 12,
};

let car: {
  name: string;
  id: string;
  age: number;
} = {
  name: "",
  id: "",
  age: 3,
};

let items: (string | number)[] = [2, "adf", 2];

function increment() {
  return num.value++;
}

function generateFullName(firstName: string, lastName: string): string {
  return (fullName.value = firstName + " " + lastName);
}
</script>
