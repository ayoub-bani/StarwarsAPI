<template>
  <div id="app">
    <HelloWorld id="1" />
    <HelloWorld id="7" />
  </div>
</template>

<script>
  import HelloWorld from './components/HelloWorld.vue'

  export default {
    name: 'App',
    components: {
      HelloWorld
    }
  }
</script>

<style>

</style>