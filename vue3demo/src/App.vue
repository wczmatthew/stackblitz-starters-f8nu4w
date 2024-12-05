<script setup>
import HelloWorld from './components/HelloWorld.vue';
import TheWelcome from './components/TheWelcome.vue';
import { ref } from 'vue';

const span = ref('<span style="color:red">This should bw 1223red.---</span>');
const count = ref(0);

function increment(event) {
  count.value++;
  span.value =
    '<button type="button" @click="increment">count is' +
    count.value +
    '</button>';
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
    {{ span }}-{{ count }}
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
