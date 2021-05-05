<template>
  <fieldset class="st-input" :class="{ 'has-error': hasError, 'st-input--is-dark' : color === 'dark', 'st-input--is-not-empty' : modelValue.length > 0 }">
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
    <label>{{ hasError ? errorMessages : label }}</label>
  </fieldset>
</template>

<script>
import {ref} from 'vue';
export default {
  name: 'StInput',  props: {
    color: {
            type: String,
      required: false,
      default: () => {
        return 'default'
      },
      validator: (value) => {
        return ['default', 'dark'].includes(value)
      }
    },
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
    errorMessages: {
      type: String,
      required: false,
      default: () => {
        return null
      }
    },
    label: {
      type: String,
      required: false,
      default: () => {
        return 'No label'
      }
    }
  },
  emits: ['update:modelValue'],
  setup(props, {emit}) {
    let innerValue = ref('');
    function inputChange(value) {
      innerValue.value = value;
      emit('update:modelValue', value)
    }

    return {
      inputChange,
      innerValue
    }
  },

}
</script>

<style>
@import '../styles/components/StInput/StInput.css';
</style>
