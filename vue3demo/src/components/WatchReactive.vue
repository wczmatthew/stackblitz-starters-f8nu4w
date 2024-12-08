<template>
  <div>
    <p>{{ obj.count }}</p>
    <p>newCount = {{ newCount }}</p>
    <button @click="obj.count++">Increment</button>
  </div>
</template>

<script setup>
import { reactive, ref, watch } from 'vue';

const obj = reactive({count: 0});
const newCount = ref(0);

watch(
  obj.count,
  (newValue) => {
    console.log(`The new count is: ${newValue}`);
    newCount.value = newValue;
  }
 )
</script>
