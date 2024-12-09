<template>
    <div>
        <button @click="enlargeText">点击</button>
        <h1>{{ title }}</h1>
    </div>
</template>

<script setup>
    import { ref } from 'vue';

    defineProps(['title']);
    const emit = defineEmits(['enlarge-text']);
    const count = ref(0);

    function enlargeText(){
        emit('enlarge-text');
        console.log('count  = ' + count.value);
    };
</script>