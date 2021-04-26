<template>
  <div class="st-tag">
    <slot />
  </div>
</template>

<script>
export default {
  name: 'StTag',
  props: {
    color: {
      type: String,
      required: false,
      default: () => {
        return 'success'
      },
      validator: (value) => {
        ['success'].includes(value)
      }
    }
  },
  setup() {
    return {}
  }
}
</script>

<style scoped>
.st-tag {
  background: var(--mint200);
  border-radius: 2px;
  font-family: Noto Sans;
  font-style: normal;
  font-weight: bold;
  font-size: 12px;
  line-height: 24px;
  display: inline-flex;
  align-items: center;
  letter-spacing: 0.12px;
  padding: 0 5px;
  height: 24px;
  color: var(--mint700);
}
</style>
