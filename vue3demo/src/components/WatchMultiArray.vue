<template>
  <div>
    <p>Number: {{ number }}</p>
    <p>doubleNumber: {{ doubleNumber }}</p>
    <p>tripleNumber: {{ tripleNumber }}</p>
    <button @click="number++">Increment</button>
  </div>
</template>

<script setup>
import { ref, computed, watch } from 'vue';

const number = ref(0);
const doubleNumber = computed(() => number.value * 2);
const tripleNumber = computed(() => number.value * 3);
console.log('aaa')
watch(
  [() => number.value, () => doubleNumber.value, () => tripleNumber.value],
  ([newValue, newValueDouble, newValueTriple], [oldValue, oldValueDouble, oldValueTriple]) => {
    console.log(`New number is ${newValue} oldValue is ${oldValue}`);
    console.log(`New double number is ${newValueDouble} oldValue is ${oldValueDouble}`);
    console.log(`New triple number is ${newValueTriple} oldValue is ${oldValueTriple}`);
  },
  { immediate: true },
  {
    flush: 'post'
  }
);
</script>
