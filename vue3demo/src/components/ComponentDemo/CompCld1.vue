<template>
    <button @click="handleClick">点击</button>
</template>

<script setup>
    import { ref } from 'vue';
    const count = ref(0);

    function handleClick(){
        console.log(count.value++);
    };
</script>