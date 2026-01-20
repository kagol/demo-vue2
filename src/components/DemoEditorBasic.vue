<template>
  <div id="editor">
    <p>Hello TinyEditor!</p>
  </div>
</template>

<script>
  import FluentEditor from '@opentiny/fluent-editor'

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  mounted() {
    // 执行初始化时，请确保能获取到 DOM 元素，如果是在 Vue 项目中，需要在 onMounted 事件中执行。
    const editor = new FluentEditor('#editor', {
      theme: 'snow',
    })
    console.log('editor', editor);
    
  }
}
</script>
