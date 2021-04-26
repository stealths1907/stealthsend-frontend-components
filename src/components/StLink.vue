<template>
  <router-link v-if="to" :to="to" class="st-link" tag="a">
    <slot></slot>
  </router-link>
  <a v-else class="st-link" href="" @click.prevent="handleClick">
    <slot></slot>
  </a>
</template>

<script>
export default {
  props: {
    to: {
      type: String,
      required: false,
      default: () => {
        return null
      }
    }
  },
  emits: ['click'],
  setup(props, ctx) {
    function handleClick() {
      ctx.emit('click')
    }
    return {
      handleClick
    }
  }
}
</script>

<style>
@import '../styles/components/StLink/StLink.css';
</style>
