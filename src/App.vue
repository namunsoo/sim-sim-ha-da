<template>
  <div id="app">
    <Main />
  </div>
</template>

<script>
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Main
  }
}
</script>

<style>
#app {
  width: 100%;
  height: 100%;
  min-width: 1500px;
  min-height: 750px;
  position: fixed;
  background-color: #1e1e1e;
}
</style>
