<template>
  <fieldset
    class="st-form-item"
    :class="[
      color === 'default' ? 'st-form-item--light' : 'st-form-item--dark',
      checkSize,
      { 'st-form-item__filled': (filled && filled.length) || filled },
      { 'st-form-item__error': errorMessage.length },
      { 'st-form-item__disabled': disabled },
      { 'st-form-item__readonly': readonly },
      { 'st-form-item--center': position === 'center' },
    ]"
  >
    <label class="label">
      <span class="label-left">{{ label }}</span>
      <span v-if="$slots.labelRight" class="label-right"
        ><slot name="labelRight"
      /></span>
    </label>
    <slot />
    <p v-if="errorMessage.length" class="st-form-item__error">
      {{ errorMessage[0] }}
    </p>
    <template v-else>
      <div v-if="$slots.description" class="description">
        <slot name="description" />
      </div>
    </template>
  </fieldset>
</template>

<script>
import { ref, computed } from 'vue'
export default {
  name: 'StFormItem',
  props: {
    color: {
      type: String,
      required: false,
      default: () => {
        return 'default'
      },
      validator: (value) => {
        return ['default', 'dark'].includes(value)
      },
    },
    size: {
      type: String,
      required: false,
      default: () => {
        return 'sm'
      },
      validator: (value) => {
        return ['sm', 'md', 'lg', 'xl'].includes(value)
      },
    },
    filled: {
      type: [String, Object, Number],
      default: () => {
        return ''
      },
    },
    label: {
      type: String,
      required: false,
      default: '',
    },
    labelRight: {
      type: String,
      required: false,
      default: '',
    },
    disabled: {
      type: Boolean,
      default: false,
    },
    readonly: {
      type: Boolean,
      required: false,
      default: () => {
        return false
      },
    },
    position: {
      type: String,
      default: '',
    },
    errorMessage: {
      type: [String, Array],
      required: false,
      default: '',
    },
  },
  emits: ['rightLabelClick'],
  setup(props, ctx) {
    const checkSize = computed(() => {
      let size = ref('sm')
      if (props.size === 'sm') {
        size = 'st-form-item--sm'
      } else if (props.size === 'md') {
        size = 'st-form-item--md'
      } else if (props.size === 'lg') {
        size = 'st-form-item--lg'
      } else if (props.size === 'xl') {
        size = 'st-form-item--xl'
      }
      return size
    })
    function handleActionLabelClick() {
      ctx.emit('rightLabelClick')
    }
    return {
      checkSize,
      handleActionLabelClick,
    }
  },
}
</script>

<style scoped>
@import '../styles/components/StFormItem/StFormItem.css';
</style>
