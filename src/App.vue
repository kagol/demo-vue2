<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <!-- <DemoEditorBasic /> -->
    <DemoEditor />
  </div>
</template>

<script>
import DemoEditor from './components/DemoEditor.vue';

// import HelloWorld from './components/HelloWorld.vue'
// import DemoEditorBasic from './components/DemoEditorBasic.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld,
    // DemoEditorBasic
    DemoEditor
  }
}
</script>

<style>
  @import '@opentiny/fluent-editor/style.css';
</style>
