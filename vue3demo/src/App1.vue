<script setup>
import HelloWorld from './components/HelloWorld.vue';
import TheWelcome from './components/TheWelcome.vue';
// import Compute from './components/Compute.vue';
import App from './App.vue';

import { ref, reactive, computed } from 'vue';
const routes = {
  '/': App,
  '/hello': HelloWorld,
  // '/compute': Compute,
};

const currentPath = ref(window.location.hash);
window.addEventListener('hashchange', () => {
  currentPath.value = window.location.hash;
});
const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || '/'] || NotFound;
});

const span = ref('<span style="color:red">This should bw 1223red.---</span>');
const count = ref(0);
const state = reactive({ total: 2 });
const books = reactive([ref('Vue 3 Guide'), ref('Vue 2 Guide')]);

const object = { id: ref(19) };
const { id } = object;
console.log('idxx id = ' + object.id.value);

const object1 = { id: ref(29) };
function increment(event) {
  count.value++;
  state.total++;

  // id++;
  console.log('object.id = ' + id.value++);

  span.value =
    '<button type="button" @click="increment">count is' +
    count.value +
    '---total :' +
    state.total +
    '</button>';
  // 这里需要 .value
  console.log(books[count.value % 2].value);
}
</script>

<template>
  <header>
    <img
      alt="Vue logo"
      class="logo"
      src="./assets/logo.svg"
      width="125"
      height="125"
      @click="increment"
    />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
    <div>****{{ span }}</div>
    <div>-{{ count }}</div>
    <div>-id1 = {{ id }}</div>
    <div>-id2 : {{ id + 1 }}****</div>
    <div>-obj1 id : {{ object1.id }}</div>
    <a href="#/">App Home</a>
    <a href="#/hello">Hello</a>
    <component :is="currentView" />
    <div v-html="span"></div>
    <button type="button" @click="increment">count is {{ count }}</button>
    <div v-html="count"></div>
  </header>

  <main>
    <TheWelcome />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
