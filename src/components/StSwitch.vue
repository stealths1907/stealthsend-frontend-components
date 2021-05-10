<template>
    <div class="st-switch"  :class="{'st-switch--is-off': !isOn}" @click="toggle">
    <div class="st-switch__label">
        <svg width="9" height="12" viewBox="0 0 9 12" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M5.5 5l1-5-6 7h3l-1 5 6-7h-3z" :fill="[isOn ? '#E0D3FC' : '#4E00F6']"/></svg>
    </div>
  </div>
</template>

<script>
import {ref} from 'vue'
    export default {
        name: 'StSwitch',
        emits: ['input'],
        setup(_, ctx) {
            const isOn = ref(false)
            function toggle() {
                isOn.value = !isOn.value
                ctx.emit('input', isOn.value)
            }

            return {
                toggle,
                isOn
            }
        }
    }
</script>

<style scoped>
.st-switch {
  cursor: pointer;
  -webkit-user-select: none;
     -moz-user-select: none;
      -ms-user-select: none;
          user-select: none;
  background: transparent;
  width: 60px;
  border: 1.5px solid var(--grey200);
  border-radius: 1.5rem;
  display: inline-flex;
  flex-direction: column;
  height: 26px;
  transition: 0.3s;
}
.st-switch.st-switch--is-off {
  /* background-color: #fce5e8; */
  /* border-color: #fbdde0; */
}
.st-switch.st-switch--is-off .st-switch__label {
  background: var(--grey50);
  color: var(--marine500);
  /* align-self: flex-end; */
  transform: translateX(33px);


    margin-top: 1px;
    margin-right: 1px;
}
.st-switch__label {
  width: 24px;
  height: 24px;
  line-height: 1.5rem;
  text-align: center;
  font-size: 0.6rem;
  background: var(--marine800);
  color: #fff;
  border-radius: 50%;

      margin-top: 1px;
    margin-left: 1px;
        display: flex;
    align-items: center;
    justify-content: center;
}
</style>