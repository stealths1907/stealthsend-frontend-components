<template>
  <span
    :id="position"
    :class="[tooltip ? 'tooltip' : '']"
    :tooltip="tooltip"
    :position="position"
    ><slot
  /></span>
</template>

<script>
import { onMounted } from 'vue'
export default {
  props: {
    tooltip: {
      type: String,
      required: true,
      default: ''
    },
    position: {
      type: String,
      default: 'top'
    }
  },
  setup(props) {
    onMounted(() => {
      if (props.position === 'center') {
        var element = document.getElementById('center')
        var pseudoBeforeWidth = window.getComputedStyle(element, ':before')
          .width
        var width = Number(pseudoBeforeWidth.split('px')[0]) + 40
        document.documentElement.style.setProperty('--left', `${width / 2}px`)
      }
    })

    return {}
  }
}
</script>

<style scoped>
:root {
  --left: 0;
}
.tooltip {
  position: relative;
}
.tooltip:hover:before,
.tooltip:hover:after {
  opacity: 1;
}
[tooltip]:before {
  pointer-events: none;
  content: attr(tooltip);
  position: absolute;
  z-index: 1;
  display: block;
  padding: 4px 20px;
  background-color: var(--background50);
  box-shadow: 0px 0px 16px rgba(0, 0, 0, 0.12);
  opacity: 0;
  color: var(--grey800);
  font-family: var(--secondary-font);
  font-size: 10px;
  line-height: 16px;
  letter-spacing: 0.12px;
  font-weight: 700;
  white-space: nowrap;
  transition: 0.3s;
}
/* [tooltip]:after {
  pointer-events: none;
  content: '';
  display: block;
  width: 0;
  height: 0;
  border-left: 3px solid transparent;
  border-right: 3px solid transparent;
  border-bottom: 5px solid black;
  position: absolute;
  z-index: 2;
  opacity: 0;
  transition: 0.3s;
} */
/* BOTTOM RIGHT */
/* [tooltip][position^='bottom-right']:before {
  top: calc(100% + 5px);
  left: calc(50% - 13px);
  padding-left: 30px;
}
[tooltip][position^='bottom-right']:after {
  top: calc(100% + 15px);
  left: 50%;
} */
/* RIGHT */
[tooltip][position^='right']:before {
  top: calc(50% - 12px);
  left: calc(100% + 12px);
  /* padding-left: 30px; */
}
/* [tooltip][position^='right']:after {
  top: calc(50% - 2px);
  left: calc(100% + 17px);
  transform: rotate(-90deg);
} */
/* TOP RIGHT */
/* [tooltip][position^='top-right']:before {
  bottom: calc(100% + 5px);
  left: calc(50% - 13px);
  padding-left: 30px;
}
[tooltip][position^='top-right']:after {
  bottom: calc(100% + 15px);
  left: 50%;
  transform: rotate(180deg);
} */
/* BOTTOM LEFT */
/* [tooltip][position^='bottom-left']:before {
  top: calc(100% + 5px);
  right: calc(50% - 13px);
  padding-right: 30px;
}
[tooltip][position^='bottom-left']:after {
  top: calc(100% + 15px);
  right: 50%;
} */
/* LEFT */
/* [tooltip][position^='left']:before {
  top: calc(50% - 12px);
  right: calc(100% + 5px);
  padding-right: 30px;
}
[tooltip][position^='left']:after {
  top: calc(50% - 2px);
  right: calc(100% + 17px);
  transform: rotate(90deg);
} */
/* TOP */
[tooltip][position^='top']:before {
  top: calc(0% - 30px);
  right: 50%;
  transform: translateX(50%);
}
/* TOP LEFT */
/* [tooltip][position^='top-left']:before {
  bottom: calc(100% + 5px);
  right: calc(50% - 13px);
  padding-right: 30px;
}
[tooltip][position^='top-left']:after {
  bottom: calc(100% + 15px);
  right: 50%;
  transform: rotate(180deg);
} */
/* CENTER */
/* [tooltip][position^='center']:before {
  top: calc(50% - 12px);
  left: calc(50% - var(--left));
}
[tooltip][position^='center']:after {
  display: none;
} */
</style>
