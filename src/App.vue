<template>
  <div class="uikit-container">
    <h1>UI Kit</h1>
    <h2>TOGGLE</h2>
    <StSwitch v-model="isSwitch">Test</StSwitch>
    <StSwitch v-model="isSwitch" type="thunder"> Test</StSwitch>
    <div style="background-color: #140435; padding: 10px;">
      <StSwitch v-model="isSwitch" theme="dark">Test</StSwitch>
      <StSwitch v-model="isSwitch" theme="dark" type="thunder"> Test</StSwitch>
    </div>
    {{ isSwitch }}
    <h2>ICONS</h2>
    <StIcon name="chart"></StIcon>
    <h2>Tag</h2>
    <StTag>+280.39%</StTag>
    <h2>Buttons</h2>
    <StButton color="secondary" @click="clickHandler('aaaaa')">Dash</StButton>
    <StButton @click="clickHandler('bbbbbaaaaaaaaaaaaaaaa')">Settings</StButton>
    <br />
    <br />
    <h2>Inputs</h2>
    <div style="padding: 10px;">
      <!-- <StAmount label="Amount" v-model="bla" placeholder="Amount"
        ><svg
          width="19"
          height="16"
          viewBox="0 0 19 16"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M10.4445 11.5557L14.2222 14.2223L18 11.5557"
            stroke="#E5E4E8"
            stroke-width="2"
          />
          <path
            d="M14.2222 14.2222L14.2222 1.77773"
            stroke="#E5E4E8"
            stroke-width="2"
          />
          <path
            d="M4.77777 1.77783V14.2223"
            stroke="#E5E4E8"
            stroke-width="2"
          />
          <path
            d="M1 4.4445L4.77778 1.77783L8.55555 4.4445"
            stroke="#E5E4E8"
            stroke-width="2"
          />
        </svg>
      </StAmount> -->
    </div>
    <div style="background-color: #140435; padding: 10px;">
      <StAmount
        v-model="blabla"
        label="Amount"
        color="dark"
        placeholder="Amount"
        ><svg
          width="19"
          height="16"
          viewBox="0 0 19 16"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M10.4445 11.5557L14.2222 14.2223L18 11.5557"
            stroke="#E5E4E8"
            stroke-width="2"
          />
          <path
            d="M14.2222 14.2222L14.2222 1.77773"
            stroke="#E5E4E8"
            stroke-width="2"
          />
          <path
            d="M4.77777 1.77783V14.2223"
            stroke="#E5E4E8"
            stroke-width="2"
          />
          <path
            d="M1 4.4445L4.77778 1.77783L8.55555 4.4445"
            stroke="#E5E4E8"
            stroke-width="2"
          />
        </svg>
      </StAmount>
    </div>
    <StInput v-model="bla" readonly placeholder="aaaa"
      ><svg
        width="19"
        height="16"
        viewBox="0 0 19 16"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M10.4445 11.5557L14.2222 14.2223L18 11.5557"
          stroke="#E5E4E8"
          stroke-width="2"
        />
        <path
          d="M14.2222 14.2222L14.2222 1.77773"
          stroke="#E5E4E8"
          stroke-width="2"
        />
        <path d="M4.77777 1.77783V14.2223" stroke="#E5E4E8" stroke-width="2" />
        <path
          d="M1 4.4445L4.77778 1.77783L8.55555 4.4445"
          stroke="#E5E4E8"
          stroke-width="2"
        />
      </svg>
    </StInput>
    <div style="background-color: #140435; padding: 10px;">
      <StInput v-model="bla" readonly color="dark" placeholder="aaaa"
        ><svg
          width="19"
          height="16"
          viewBox="0 0 19 16"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M10.4445 11.5557L14.2222 14.2223L18 11.5557"
            stroke="#E5E4E8"
            stroke-width="2"
          />
          <path
            d="M14.2222 14.2222L14.2222 1.77773"
            stroke="#E5E4E8"
            stroke-width="2"
          />
          <path
            d="M4.77777 1.77783V14.2223"
            stroke="#E5E4E8"
            stroke-width="2"
          />
          <path
            d="M1 4.4445L4.77778 1.77783L8.55555 4.4445"
            stroke="#E5E4E8"
            stroke-width="2"
          />
        </svg>
      </StInput>
    </div>
    <StInput
      v-model="bla"
      has-error
      :error-messages="'custom error message'"
    ></StInput>
    <br />
    <br />
    <h2>Link</h2>
    <StLink to="settings">hoveraj me burki</StLink>
    <StLink to="settings">hoveraj me burki</StLink>
    <br />
    <br />
    <StLink @click="clickHandler('bla')">ovaj samo ima emit</StLink>
    <h2>Radio</h2>
    <br />
    <br />
    <StRadio v-model="radioValue" :name="'uikitradio'" value="option 1"
      >option 1</StRadio
    >
    <StRadio v-model="radioValue" :name="'uikitradio'" value="option 2"
      >option 2</StRadio
    >
    <StRadio
      v-model="radioValue"
      type="square"
      :name="'uikitradio'"
      value="option 3"
      >option 1</StRadio
    >
    <StRadio
      v-model="radioValue"
      type="square"
      :name="'uikitradio'"
      value="option 4"
      >option 2</StRadio
    >
    {{ radioValue }}
    <br />
    <br />
    <h2>Checkbox</h2>

    <StCheckbox v-model="checkboxPrvi"
      >checkbox usrani {{ checkboxPrvi }}</StCheckbox
    >
    <StCheckbox
      >checkbox usrani veliki Lorem ipsum dolor sit amet, consectetur
      adipisicing elit. Nemo iure doloremque accusantium, beatae doloribus
      minima? Ut voluptas accusantium accusamus repellendus? Perferendis rerum
      voluptates sequi incidunt, magnam quidem in. Magni, illum?Lorem ipsum
      dolor sit amet consectetur adipisicing elit. Minus itaque eos consectetur
      perferendis laborum facere expedita, iste quod voluptatibus officiis
      dolorem delectus accusantium aut vero fugiat adipisci eaque perspiciatis
      beatae!</StCheckbox
    >
    <br /><br />
    <h2>Modal</h2>
    <StModal
      show-back-button
      :steps="3"
      :current-step="currentStep"
      :visible="showModal"
      light
      @close="showModal = false"
      @back="goBack"
    >
      <template #header> Modal title </template>
      <template #body>
        <div v-if="currentStep === 1">
          <StInput
            v-model="accountModal"
            color="dark"
            label="Account"
          ></StInput>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolores,
          aspernatur? Necessitatibus hic a ullam commodi! Nostrum deserunt
          facere ut ducimus unde in, animi qui soluta, omnis praesentium,
          incidunt voluptatum quae.
        </div>
        <div v-if="currentStep === 2">
          sadasdasdads
        </div>
      </template>
      <template #footer>
        <StButton color="secondary" @click="showModal = false">Cancel</StButton>
        <StButton color="white" @click="currentStep = 2">Submit</StButton>
      </template>
    </StModal>
    <button @click="showModal = true">Show modal</button>
    <br /><br />
    <h2>Select</h2>
    <StMultiselect
      v-model="multiselectValue"
      :can-deselect="false"
      :options="multiselectOptions"
    />
    <br />
    <br />
    <h2>Table</h2>
    <StTable :data="tableData" :columns="tableColumns"></StTable>
    <StPagination
      :total="Number(85)"
      :page-size="Number(10)"
      :current-page="Number(9)"
    ></StPagination>
    <br /><br />
    <h2>Status</h2>
    <StStatus type="red">Missed</StStatus>
    <StStatus type="green">Produced</StStatus>
    <StStatus type="orange">Late</StStatus>
    <StStatus type="empty">Scheduled</StStatus>
    <br /><br />
    <h2>Dropdown</h2>
    <StDropdown
      :items="[
        { to: 'settings', label: 'Settings' },
        { to: 'dashboard', label: 'Dash' }
      ]"
      >click me</StDropdown
    >
    <br /><br />
    <h2>Copy to clipboard</h2>
    <StTooltip
      :tooltip-text="copyPending ? 'Copied to clipboard!' : 'Click to copy'"
    >
      <StClipboard content="kopirani string" @click="handleCopy"></StClipboard>
    </StTooltip>
    <br />
    <br />
    <h2>Tooltip</h2>
    <StTooltip position="left" tooltip-text="aaaaa">
      <button>left</button>
    </StTooltip>
    <StTooltip tooltip-text="aaaaa">
      <button>top</button>
    </StTooltip>
    <StTooltip position="bottom" tooltip-text="aaaaa">
      <button>bottom</button>
    </StTooltip>
    <StTooltip position="right" tooltip-text="aaaaa">
      <button>right</button>
    </StTooltip>
    <br />
    <br />
    <h2>Global loading</h2>
    <button @click="toggleLoading">Trigger global loading</button>
    <StLoading :visibility="isLoading"></StLoading>
  </div>
</template>

<script>
import { ref } from 'vue'
import StButton from './components/StButton.vue'
import StCheckbox from './components/StCheckbox.vue'
import StClipboard from './components/StClipboard.vue'
import StDropdown from './components/StDropdown.vue'
import StInput from './components/StInput.vue'
import StAmount from './components/StAmount.vue'
import StLink from './components/StLink.vue'
import StLoading from './components/StLoading.vue'
import StModal from './components/StModal.vue'
import StPagination from './components/StPagination.vue'
import StRadio from './components/StRadio.vue'
import StStatus from './components/StStatus.vue'
import StTable from './components/StTable.vue'
import StSwitch from './components/StSwitch.vue'
import StTooltip from './components/StTooltip.vue'
import StTag from './components/StTag.vue'
import StIcon from './components/StIcon.vue'

export default {
  name: 'App',
  components: {
    StButton,
    StIcon,
    StLink,
    StCheckbox,
    StRadio,
    StInput,
    StAmount,
    StLoading,
    StModal,
    StPagination,
    StStatus,
    StTable,
    StSwitch,
    StDropdown,
    StClipboard,
    StTooltip,
    StTag
  },
  setup() {
    const bla = ref('')
    const blabla = ref(null)
    const showModal = ref(false)
    const accountModal = ref('test dummy')
    const currentStep = ref(1)
    const checkboxPrvi = ref(false)
    const radioValue = ref('option 1')
    const isSwitch = ref(false)
    const tableData = ref([
      {
        address: 'RxLvZSm4gMmzoS5VyJxm24FaGDRJjVPv9z',
        protocol: 62200,
        subVersion: '2.2.0',
        blockHeight: '12345678'
      },
      {
        address: '4b5t45z45zb45zb45bz45bz45zb45zb454',
        protocol: 62200,
        subVersion: '2.2.0',
        blockHeight: '556756756'
      },
      {
        address: '56un56un56u56un56un56u5u56n56un56u',
        protocol: 62200,
        subVersion: '2.2.0',
        blockHeight: '7878787887'
      },
      {
        address: '67imi67im67im67im67i67i67i6767m6mm',
        protocol: 62200,
        subVersion: '2.2.0',
        blockHeight: '6776676767'
      },
      {
        address: 'rbrthrthrhrthrhthbrbhrthbrbthrtbhr ',
        protocol: 62200,
        subVersion: '2.2.0',
        blockHeight: '454353353535'
      },
      {
        address: 'vbbcvbcvbcvbcvbcbcvbvbcvbcvbcvbcvb',
        protocol: 62200,
        subVersion: '2.2.0',
        blockHeight: '67677667'
      },
      {
        address: 'mbnnmbmnbmbnmbnmbnmbnmbmbnmbnmbnmm',
        protocol: 62200,
        subVersion: '2.2.0',
        blockHeight: '7676767'
      },
      {
        address: 'qweqeqweqqwewqewqeqeqewqweqwewqqwe',
        protocol: 62200,
        subVersion: '2.2.0',
        blockHeight: '12345678'
      }
    ])
    const tableColumns = ref([
      { key: 'address', title: 'Address' },
      { key: 'protocol', title: 'Protocol' },
      {
        key: 'subVersion',
        title: 'Sub-version',
        customCellClass: 'cell-center',
        customHeaderClass: 'cell-center'
      },
      { key: 'blockHeight', title: 'Blockheight' }
    ])
    function goBack(step) {
      currentStep.value = step
    }
    return {
      bla,
      blabla,
      tableData,
      tableColumns,
      showModal,
      accountModal,
      currentStep,
      goBack,
      checkboxPrvi,
      radioValue,
      isSwitch
    }
  },
  methods: {
    clickHandler(data) {
      console.log(data)
    }
  }
}
</script>
