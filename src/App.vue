<script setup>
import { ref } from 'vue';

const targetId = ref('200')

const scrollToElement = () =>  {
  const el = document.getElementById(targetId.value);

  if (el) {
    el.scrollIntoView();
  }
}
</script>

<template>
<div>
    <button @click="scrollToElement">Scroll to {{targetId}}</button>
    <input type="text" v-model="targetId" />
    <ul>
      <li v-for="n of 500" :key="n" :id="n">
        {{ n }}
      </li>
    </ul>
</div>
</template>

<style scoped>
ul {
  padding-lefT: 0;
}
li {
  background: #eee !important;
  list-style-type: none;
  margin-bottom: 1em;
  margin-top: 1em;
  padding: 4px;
}
</style>