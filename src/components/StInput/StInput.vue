<template>
  <fieldset class="st-input" :class="{ 'has-error': hasError }">
    <input
      ref="input"
      :type="type"
      :disabled="disabled"
      :placeholder="placeholder"
      autocomplete="off"
      class="st-input__inner"
      :class="{ 'is-disabled': disabled, 'is-dirty': modelValue.length > 0 }"
      :value="modelValue"
      @input="$emit('update:modelValue', $event.target.value)"
    />
    <label>{{ hasError ? errorMessages : label }}</label>
  </fieldset>
</template>

<script>
export default {
  name: "StInput",
  props: {
    icon: {
      type: String,
      required: false,
      default: () => {
        return "";
      }
    },
    modelValue: {
      type: String,
      required: false,
      default: () => {
        return "";
      }
    },
    disabled: {
      type: Boolean,
      required: false,
      default: () => {
        return false;
      }
    },
    type: {
      type: String,
      required: false,
      default: () => {
        return "text";
      }
    },
    placeholder: {
      type: String,
      required: false,
      default: () => {
        return "";
      }
    },
    hasError: {
      type: Boolean,
      required: false,
      default: () => {
        return false;
      }
    },
    errorMessages: {
      type: String,
      required: false,
      default: () => {
        return null;
      }
    },
    label: {
      type: String,
      required: false,
      default: () => {
        return "No label";
      }
    }
  },
  emits: ["update:modelValue"]
};
</script>

<style>
@import "../../styles/components/StInput/StInput.css";
</style>
