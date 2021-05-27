<template>
  <fieldset
    class="st-input"
    :class="{
      'has-error': hasError,
      'st-input--is-not-empty': modelValue.length > 0,
      'st-input--readonly': readonly
    }"
  >
    <input
      ref="input"
      :type="type"
      :disabled="disabled"
      :placeholder="placeholder"
      autocomplete="off"
      class="st-input__inner"
      :class="{ 'is-disabled': disabled, 'is-dirty': modelValue.length > 0 }"
      :value="modelValue"
      @input="inputChange($event.target.value)"
    />
    <div v-if="$slots.default" class="st-icon"><slot /></div>
  </fieldset>
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
