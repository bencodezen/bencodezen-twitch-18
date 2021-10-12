<script setup>
import { ref } from 'vue'

const navLinks = ref([
  {
    label: 'Home',
    url: '/'
  },
  {
    label: 'Todo',
    url: '/todo'
  },
  {
    label: 'Library',
    url: '/library'
  }
])

const userColor = ref('')
</script>

<template>
  <nav class="main-nav">
    <ul>
      <li v-for="item in navLinks">
        <nuxt-link :to="item.url">{{ item.label }}</nuxt-link>
      </li>
      <li><input type="color" v-model="userColor" /></li>
    </ul>
  </nav>
</template>

<style>
.main-nav ul {
  display: flex;
  margin: 0;
  padding: 0;
}

.main-nav li {
  margin-left: 30px;
}

.main-nav .router-link-active {
  background-color: v-bind(userColor);
}
</style>
