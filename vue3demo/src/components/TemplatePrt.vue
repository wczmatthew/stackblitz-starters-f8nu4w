<script setup>
import { onMounted, useTemplateRef } from 'vue'
import Child from './TemplateCld.vue'

const childRef = useTemplateRef('childRef')

onMounted(() => {
  // childRef.value 将持有 <Child /> 的实例
  console.log("Parent get the child = ");
  console.log(childRef.value.a.value);
})
</script>

<template>
  <Child ref="childRef" />
</template>
