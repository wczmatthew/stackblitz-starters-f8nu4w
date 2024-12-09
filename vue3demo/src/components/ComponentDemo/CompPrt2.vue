<template>
    <div :style="{fontSize: itemSize + 'px'}">
        <CompCld2 v-for="cld in children" :title="cld.title" :key="cld.id" @enlarge-text="itemSize += 2"/>
    </div>
</template>

<script setup>
import { ref } from 'vue';
import CompCld2 from './CompCld2.vue';

const itemSize = ref(16);

const children = ref([
    {id: 1, title: 'title1'},
    {id: 2, title: 'title2'},
    {id: 3, title: 'title3'},
]);
</script>