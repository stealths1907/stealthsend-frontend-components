<template>
  <button
    class="st-button"
    :class="{
      'st-button--primary': color === 'primary',
      'st-button--secondary': color === 'secondary',
      disabled: disabled
    }"
    :disabled="disabled"
    @click="(e) => $emit('click', e)"
  >
    <slot />
  </button>
</template>

<script>
export default {
  name: "StButton",
  props: {
    disabled: {
      type: Boolean,
      required: false,
      default: () => {
        return false;
      }
    },
    to: {
      type: String,
      required: false,
      default: () => {
        return "";
      }
    },
    color: {
      type: String,
      required: false,
      default: () => {
        return "primary";
      },
      validator: value => {
        return ["primary", "secondary"].includes(value);
      }
    }
  },
  emits: ["click"],
  // setup(props, ctx) {
  //   function handleClick() {
  //     if (props.to.length > 0) ctx.emit("click");
  //   }
  //   return {
  //     handleClick
  //   };
  // }
};
</script>

<style>
@import "../styles/components/StButton/StButton.css";
</style>
