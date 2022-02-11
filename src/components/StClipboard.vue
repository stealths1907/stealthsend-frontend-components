<template>
  <span class="st-clipboard" @click="copyToClipboard"
    ><slot>Copy to clipboard (click me)</slot></span
  >
</template>

<script>
import { useClipboard } from '@vueuse/core'
export default {
  name: 'StClipboard',
  props: {
    content: {
      type: String,
      required: true
    }
  },
  emits: ['click'],
  setup(props, ctx) {
    const { copy } = useClipboard()
    function copyToClipboard() {
      copy(props.content)
      ctx.emit('click')
    }
    return { copyToClipboard }
  }
}
</script>

<style scoped>
.st-clipboard:hover {
  cursor: pointer;
}
</style>
