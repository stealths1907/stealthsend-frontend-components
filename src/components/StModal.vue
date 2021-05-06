<template>
  <transition name="fade">
    <div v-if="visible" class="st-modal">
      <div class="st-modal-wrapper">
        <div ref="stModalRef" class="st-modal-container">
          <div class="st-modal__header">
            <slot name="header"> default header </slot>
            <div class="controls">
              <span
                v-if="showBackButton"
                class="st-modal__back-button"
                @click="$emit('back')"
              >
                <svg
                  width="19"
                  height="14"
                  viewBox="0 0 19 14"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M2 7h17M8 13L2 7l6-6"
                    stroke="#FAF9FC"
                    stroke-width="2"
                  />
                </svg>
              </span>
              <span
                v-if="showCloseButton"
                class="st-modal__close-button"
                @click="$emit('close')"
              >
                <svg
                  width="18"
                  height="14"
                  viewBox="0 0 18 14"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M3 1l12 12M3 13L15 1"
                    stroke="#FAF9FC"
                    stroke-width="2"
                    stroke-linejoin="round"
                  />
                </svg>
              </span>
            </div>
          </div>

          <div class="st-modal__body">
            <slot name="body"> default body </slot>
          </div>

          <div class="st-modal__footer">
            <slot name="footer">
              <!-- default footer
              <button class="modal-default-button" @click="$emit('close')">
                OK
              </button> -->
            </slot>
          </div>
          <div v-if="steps > 0" class="st-modal__stepper">
            <span
              v-for="step in steps"
              :key="step"
              class="step"
              :class="{ 'step--active': step === currentStep }"
            ></span>
          </div>
        </div>
      </div>
    </div>
  </transition>
</template>

<script>
import { onClickOutside } from '@vueuse/core'
import { ref } from 'vue'

export default {
  name: 'StModal',
  props: {
    showBackButton: {
      type: Boolean,
      required: false,
      default: () => {
        return false
      }
    },
    steps: {
      type: Number,
      required: false,
      default: () => {
        return 0
      }
    },
    currentStep: {
      type: Number,
      required: false,
      default: () => {
        return 0
      }
    },
    visible: {
      type: Boolean,
      required: false,
      default: false
    },
    showCloseButton: {
      type: Boolean,
      required: false,
      default: true
    },
    hasClickOutside: {
      type: Boolean,
      required: false,
      default: true
    }
  },
  emits: ['close', 'back'],
  setup(props, ctx) {
    const stModalRef = ref(null)

    onClickOutside(stModalRef, () => {
      if (props.hasClickOutside) {
        ctx.emit('close')
      }
    })

    return { stModalRef }
  }
}
</script>

<style scoped>
.st-modal {
  position: fixed;
  z-index: var(--zModal);
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: table;
  transition: opacity 0.3s ease;
}
.st-modal__close-button {
  cursor: pointer;
}
.st-modal__back-button {
  cursor: pointer;
  margin-right: 26px;
}
.st-modal__close-button:hover {
  cursor: pointer;
}
.st-modal__header {
  color: var(--grey50);
  font-family: var(--primary-font);
  font-weight: 700;
  font-size: 18px;
  line-height: 28px;
  letter-spacing: 0.32px;

  display: flex;
  justify-content: space-between;
  align-items: center;
}
.st-modal__body {
  margin: 45px 0 65px 0;
}
/* .st-modal__footer {
  display: flex;
  justify-content: flex-end;
} */
.st-modal__stepper {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 24px;
}
.st-modal__stepper .step {
  width: 4px;
  height: 4px;
  border-radius: 50%;
  background: var(--grey400);
  margin: 0 4px;
}

.st-modal__stepper .step--active {
  width: 4px;
  height: 4px;
  border-radius: 50%;
  background: var(--grey50);
  margin: 0 4px;
}

.st-modal-wrapper {
  display: table-cell;
  vertical-align: middle;
}
.st-modal-container {
  position: relative;
  width: 520px;
  margin: 0px auto;
  padding: 32px;
  background-color: var(--marine900);
  color: var(--grey100);
  border-radius: 2px;
  box-shadow: 4px 4px 8px rgba(20, 4, 53, 0.05),
    15px 15px 30px rgba(20, 4, 53, 0.15);
  transition: all 0.3s ease;
  font-family: var(--primary-font);
}
.modal-default-button {
  display: block;
  margin-top: 1rem;
}

.controls {
  display: flex;
  justify-content: flex-end;
}
</style>
