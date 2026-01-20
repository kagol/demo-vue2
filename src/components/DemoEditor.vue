<template>
  <div>
    <Editor v-model="htmlContent" :options="{ theme: 'snow' }" />
    <p>预览：</p>
    <div v-html="htmlContent"></div>
  </div>
</template>

<script>
import Editor from './Editor.vue'

export default {
  components: {
    Editor
  },
  data() {
    return {
      htmlContent: '<p>初始内容</p>'
    }
  }
}
</script>