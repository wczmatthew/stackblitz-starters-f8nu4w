<script setup>
import { ref, computed } from 'vue';
//import App from './App.vue';
import HelloWorld1 from './components/HelloWorld1.vue';
import HelloWorld from './components/HelloWorld.vue';
import Compute from './components/Compute.vue';
import NotFound from './components/TheWelcome.vue';
import Watch from './components/Watch.vue';
import WatchCompute from './components/WatchCompute.vue';
import WatchCompute1 from './components/WatchCompute1.vue';
import WatchGetter from './components/WatchGetter.vue';
import WatchMultiArray from './components/WatchMultiArray.vue';
import WatchReactive from './components/WatchReactive.vue';
import WatchPost from './components/WatchPost.vue';
import TemplateRef from './components/TemplateRef.vue';
import TemplateVFor from './components/TemplateVFor.vue';
import TemplateFunc from './components/TemplateFunc.vue';
import TemplatePrt from './components/TemplatePrt.vue';
const routes = {
  '/': HelloWorld1,
  '/hello': HelloWorld,
  '/compute': Compute,
  '/watch': Watch,
  '/watchCompute': WatchCompute,
  '/watchCompute1': WatchCompute1,
  '/watchGetter': WatchGetter,
  '/watchMultiArray': WatchMultiArray,
  '/watchReactive': WatchReactive,
  '/watchPost': WatchPost,
  '/templateRef': TemplateRef,
  '/templateVFor': TemplateVFor,
  '/templateFunc': TemplateFunc,
  '/templatePrt': TemplatePrt,
};
const currentPath = ref(window.location.hash);
window.addEventListener('hashchange', () => {
  currentPath.value = window.location.hash;
});
const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || '/'] || NotFound;
});

const p2c = ref('papa to child');
const p2c1 = ref('papa to child1');
</script>
<template>
  <a href="#/">Home</a> | <a href="#/hello">hello</a> |
  <a href="#/compute">compute</a> | <a href="#/watch">Watch</a> |
  <a href="#/watchCompute">WatchCompute</a> |
  <a href="#/watchCompute1">WatchCompute1</a> |
  <a href="#/watchGetter">WatchGetter</a> |
  <a href="#/watchMultiArray">WatchMultiArray</a> |
  <a href="#/watchReactive">WatchReactive</a> |
  <a href="#/watchPost">WatchPost</a> |
  <a href="#/templateRef">TemplateRef</a> |
  <a href="#/templateVFor">TemplateVFor</a> |
  <a href="#/templateFunc">TemplateFunc</a> |
  <a href="#/templatePrt">TemplatePrt</a> |
  <a href="#/non-existent-path">Broken Link</a>
  <!-- <component :is="currentView" :msg="p2c" :msg1="p2c1" /> -->
  <component :is="currentView" />
</template>
