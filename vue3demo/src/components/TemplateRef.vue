<script setup>
import { useTemplateRef, onMounted } from 'vue'

// 第一个参数必须与模板中的 ref 值匹配
const input = useTemplateRef('my-input')

onMounted(() => {
  input.value.focus()
  console.log("input.value = " + input.value.value)
})
</script>

<template>
  <input ref="my-input" value="my ref"/>
</template>
