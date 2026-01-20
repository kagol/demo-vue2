<template>
  <div class="editor-wrapper">
    <div ref="editorElement" class="editor-container"></div>
  </div>
</template>

<script>
import FluentEditor from '@opentiny/fluent-editor'

export default {
  name: 'EditorComponent',
  props: {
    value: {
      type: String,
      default: ''
    },
    options: {
      type: Object,
      default: () => ({
        theme: 'snow'
      })
    }
  },
  data() {
    return {
      editor: null,
      isInitialized: false
    }
  },
  mounted() {
    // 初始化编辑器
    this.editor = new FluentEditor(this.$refs.editorElement, this.options)
    
    // 监听编辑器内容变化
    this.editor.on('text-change', () => {
      if (!this.isUpdating) {
        const content = this.editor.root.innerHTML
        this.$emit('input', content)
      }
    })
    
    // 设置初始值
    if (this.value) {
      const delta = this.editor.clipboard.convert({ html: this.value })
      this.editor.setContents(delta, 'silent')
    }

    this.isInitialized = true
  },
  watch: {
    value(newVal) {
      if (this.isInitialized && this.editor && newVal !== this.editor.root.innerHTML) {
        const delta = this.editor.clipboard.convert({ html: newVal })
        this.editor.setContents(delta, 'silent')
      }
    }
  },
  beforeDestroy() {
    // 销毁编辑器实例
    if (this.editor) {
      this.editor = null
    }
  }
}
</script>

<style scoped>
.editor-wrapper {
  width: 100%;
}

.editor-container {
  width: 100%;
  min-height: 300px;
}
</style>
