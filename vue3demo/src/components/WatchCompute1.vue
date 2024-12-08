<template>
  <div>
    <input v-model="firstName" placeholder="First name" />
    <input v-model="lastName" placeholder="Last name" />
    <p>Full Name: {{ fullName }}</p>
  </div>
</template>

<script setup>
import { ref, computed, watch } from 'vue';

const firstName = ref('');
const lastName = ref('');

const fullName = computed(() => {
  return `${firstName.value} ${lastName.value}`;
});

// 观察 fullName 的变化
watch(fullName, (newValue) => {
  console.log(`Full name changed to: ${newValue}`);
});
</script>
