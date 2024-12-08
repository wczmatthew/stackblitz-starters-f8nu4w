<template>
  <div>
    <p>Number: {{ number }}</p>
    <p>doubleNumber: {{ doubleNumber }}</p>
    <button @click="number++">Increment</button>
  </div>
</template>

<script setup>
import { ref, computed, watch } from 'vue';

const number = ref(0);
const doubleNumber = computed(() => number.value * 2);
console.log('aaa')
watch(
  () => doubleNumber.value,
  (newValue, oldValue) => {
    console.log(`New double number is ${newValue} oldValue is ${oldValue}`)
  }
);
</script>
