<template>
  <div ref="myDiv">
    {{ message }}
  </div>
  <button @click="updateMessage">Update Message</button>
</template>

<script setup>
import { ref, watch, onMounted } from 'vue';

const message = ref('Hello, Vue 3!');
const myDiv = ref(null);

// 使用 flush: 'post' 选项，确保侦听器在 DOM 更新后被调用
watch(message,
  (newValue, oldValue) => {
    console.log('Message changed from', oldValue, 'to', newValue);
    console.log('Updated DOM content:', myDiv.value.textContent);
  },
  { flush: 'post' }
);

function updateMessage() {
  message.value = 'Hello, updated message!';
}

// 在组件挂载后打印初始 DOM 内容
onMounted(() => {
  console.log('Initial DOM content:', myDiv.value.textContent);
});
</script>
