<template>
  <div class="st-input">
    <input
      ref="input"
      :type="type"
      :disabled="disabled"
      :readonly="readonly"
      :placeholder="placeholder"
      autocomplete="off"
      class="st-input__inner"
      :value="modelValue"
      @input="inputChange($event.target.value)"
    />
    <div v-if="$slots.default" class="st-icon"><slot /></div>
  </div>
</template>

<script>
import { ref } from 'vue'
export default {
  name: 'StInput',
  props: {
    icon: {
      type: String,
      required: false,
      default: () => {
        return ''
      }
    },
    modelValue: {
      type: String,
      required: false,
      default: () => {
        return ''
      }
    },
    disabled: {
      type: Boolean,
      required: false,
      default: () => {
        return false
      }
    },
    readonly: {
      type: Boolean,
      required: false,
      default: () => {
        return false
      }
    },
    type: {
      type: String,
      required: false,
      default: () => {
        return 'text'
      }
    },
    placeholder: {
      type: String,
      required: false,
      default: () => {
        return ''
      }
    },
    hasError: {
      type: Boolean,
      required: false,
      default: () => {
        return false
      }
    },
    name: {
      type: String,
      required: false,
      default: 'missing-name'
    }
  },
  emits: ['update:modelValue'],
  setup(props, { emit }) {
    let innerValue = ref('')
    function inputChange(value) {
      innerValue.value = value
      emit('update:modelValue', value)
    }

    return {
      inputChange,
      innerValue
    }
  }
}
</script>

<style>
@import '../styles/components/StInput/StInput.css';
</style>
