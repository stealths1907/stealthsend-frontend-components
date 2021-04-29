<template>
  <component :is="myIcon" />
</template>

<script>
import { defineAsyncComponent, computed } from 'vue'
export default {
  name: 'StIcon',
  props: {
    name: {
      type: String,
      default: () => {
        return 'chart'
      }
    }
  },
  setup(props) {
    const myIcon = computed(() => {
      return defineAsyncComponent(() => import(`./icons/${props.name}`))
    })

    return {
      myIcon
    }
  }
}
</script>
