<script setup>
import { ref, onMounted } from 'vue'
const a = ref('aaa')

onMounted(() => {
  console.log('child + ' + a.value);
})

defineExpose({
  a
});
</script>

<template>
  <h1>I'm A child.   {{ a }}</h1>
</template>
