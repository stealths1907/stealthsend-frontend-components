<template>
  <button
    :class="[type, `button-${size}`]"
    :disabled="disabled"
    @click="(e) => $emit('click', e)"
  >
    <slot />
  </button>
</template>

<script>
export default {
  name: 'StButton',
  props: {
    disabled: {
      type: Boolean,
      required: false,
      default: () => {
        return false
      }
    },
    to: {
      type: String,
      required: false,
      default: () => {
        return ''
      }
    },
    type: {
      type: String,
      required: true,
      default: () => {
        return 'type-a'
      },
      validator: (value) => {
        return ['type-a', 'type-b', 'type-c', 'type-d'].includes(value)
      }
    },
    size: {
      type: String,
      required: true,
      default: () => {
        return 'normal'
      },
      validator: (value) => {
        return ['large', 'medium', 'normal', 'small', 'xsmall'].includes(value)
      }
    }
  },
  emits: ['click']
  /* setup() {
    function handleClick() {
      if (props.to.length > 0) ctx.emit("click");
    }
    return {
      handleClick
    };
  } */
}
</script>

<style>
@import '../styles/components/StButton/StButton.css';
</style>
