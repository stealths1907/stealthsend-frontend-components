<template>
  <div class="st-tag"
      :class="{
      'st-tag--is-success': color === 'success',
      'st-tag--is-danger': color === 'danger',
    }"
  >
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
        return ['success', 'danger'].includes(value)
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
  border-radius: 2px;
  font-family: var(--secondary-font);
  font-style: normal;
  font-weight: bold;
  font-size: 12px;
  line-height: 24px;
  display: inline-flex;
  align-items: center;
  letter-spacing: 0.12px;
  padding: 0 5px;
  height: 24px;
}
.st-tag--is-success {
  color: var(--mint700);
  background: var(--mint200);
}
.st-tag--is-danger {
  color: var(--mint700);
  background: var(--mint200);
}
</style>
