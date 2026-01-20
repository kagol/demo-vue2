<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <DemoEditorBasic />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import DemoEditorBasic from './components/DemoEditorBasic.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld,
    DemoEditorBasic
  }
}
</script>

<style>
  @import '@opentiny/fluent-editor/style.css';
</style>
