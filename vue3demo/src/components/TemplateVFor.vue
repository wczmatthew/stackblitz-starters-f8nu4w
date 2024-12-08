<script setup>
import { ref, useTemplateRef, onMounted } from 'vue'

const list = ref([
  'VW',
  'BUICK',
  'HONDA',
  'TOYOTA',
  'MAZDA'
])

const itemRefs = useTemplateRef('items')

onMounted(() => {
  console.log(itemRefs.value)
  console.log(itemRefs.value[0])
})
</script>

<template>
  <ul>
    <li v-for="item in list" ref="items">
      <p style="color: red">{{ item }}</p>
    </li>
  </ul>
</template>
