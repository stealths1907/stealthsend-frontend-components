<template>
  <label class="st-radio" :for="id">
    <span class="st-radio__label">
      <slot></slot>
    </span>
    <input
      :id="id"
      :name="name"
      type="radio"
      class="st-radio__input"
      :value="label"
      @input="$emit('update:modelValue', label)"
    />
    <span class="st-radio__checkmark"></span>
  </label>
</template>

<script>
// import { ref } from 'vue'
export default {
  name: "StRadio",
  props: {
    id: {
      type: String,
      required: true
    },
    modelValue: {
      type: String,
      required: true
    },
    name: {
      type: String,
      required: true
    },
    label: {
      type: String,
      required: true
    }
  },
  emits: ["update:modelValue"]
};
</script>

<style>
@import "../styles/components/StRadio/StRadio.css";
</style>
