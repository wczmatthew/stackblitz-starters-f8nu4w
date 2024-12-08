<script setup>
import { onMounted } from 'vue'

// 第一个参数必须与模板中的 ref 值匹配
// const input = useTemplateRef('my-input')

onMounted(() => {
  // input.value.focus()
  // console.log("input.value = " + input.value.value)
  console.log("mounted")
})
</script>

<template>
  <input :ref="(el) => { console.log(el); el.focus();}" value="my ref"/>
</template>
