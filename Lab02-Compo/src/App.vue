<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import { useMessageStore } from './stores/message';
import { storeToRefs } from 'pinia';
const store = useMessageStore()
const { message } = storeToRefs(store)
</script>

<template>
  <header>
    <div id="flashMessage" v-if="message">
    <h4>{{ message }}</h4>
    </div>
    <nav>
      <RouterLink :to="{name: 'EventList'}">Home</RouterLink>
      <RouterLink :to="{name: 'about'}">About</RouterLink>
      <RouterLink :to="{name: 'Component'}">Component</RouterLink>
      <RouterLink :to="{name: 'Student'}">Student</RouterLink>
    </nav>
  </header>

  <RouterView />
</template>

<style>
#app {
  front-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-front-smoothing: antialiased;
  -moz-osx-front-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
nav {
  padding: 30px;
}

nav a {
  front-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}

header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

h4 {
  front-size: 20px;
}

@keyframes yellowfade {
  from {
    background: yellow;
  }
  to {
    background: transparent;
  }
}

#flashMessage {
  animation: yellowfade 3s ease-in-out
}
</style>
