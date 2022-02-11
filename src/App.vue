<template>
  <div class="ui-container">
    <div class="tabs">
      <a
        class="tabs-link"
        :class="{ 'tabs-link__active': activeTab === 'input' }"
        @click="changeTab('input')"
        >Input</a
      >
      <a
        class="tabs-link"
        :class="{ 'tabs-link__active': activeTab === 'button' }"
        @click="changeTab('button')"
        >Button</a
      >
      <a
        class="tabs-link"
        :class="{ 'tabs-link__active': activeTab === 'checkbox' }"
        @click="changeTab('checkbox')"
        >Checkbox</a
      >
      <a
        class="tabs-link"
        :class="{ 'tabs-link__active': activeTab === 'radio' }"
        @click="changeTab('radio')"
        >Radio</a
      >
      <a
        class="tabs-link"
        :class="{ 'tabs-link__active': activeTab === 'tags' }"
        @click="changeTab('tags')"
        >Tags</a
      >
      <a
        class="tabs-link"
        :class="{ 'tabs-link__active': activeTab === 'toggle' }"
        @click="changeTab('toggle')"
        >Toggle</a
      >
      <a
        class="tabs-link"
        :class="{ 'tabs-link__active': activeTab === 'tooltip' }"
        @click="changeTab('tooltip')"
        >Tooltip</a
      >
    </div>
    <div class="ui-container__inner">
      <template v-if="activeTab === 'input'">
        <h1>Input</h1>
        <div>
          <div class="light grid">
            <StFormItem label="Label sm" :filled="input">
              <template #labelRight>Optional</template>
              <StInput v-model="input" placeholder="Field value">
                <svg
                  width="18"
                  height="18"
                  viewBox="0 0 18 18"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M12 13H18M14 9H18"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                  <circle
                    cx="8"
                    cy="5"
                    r="4"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                  <path
                    d="M8.3125 9C5.0625 9 9.9375 9 6.6875 9C3.4375 9 1 11.4 1 13.8C1 16.2 1 17 1 17H18"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                </svg>
                <svg
                  width="18"
                  height="18"
                  viewBox="0 0 18 18"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M7 7H1V1H7V7Z"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M11 0V3H14V1H17V5"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M7 18V16H4V17H1V14"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M11 18V16H14V17H17V14"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path d="M11 13H7V11H4" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M10 7H18" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M14 9V11H17V9" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M1 10V12" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M11 9V10.6364" stroke="#6B2AF7" stroke-width="2" />
                </svg>
              </StInput>
              <template #description>
                <p>Description/help text</p>
                <p>Description/help text</p>
              </template>
            </StFormItem>
            <StFormItem label="Label md" :filled="input" size="md">
              <template #labelRight>Optional</template>
              <StInput v-model="input" placeholder="Field value"></StInput>
            </StFormItem>
            <StFormItem label="Label lg" :filled="input" size="lg">
              <template #labelRight>Optional</template>
              <StInput v-model="input" placeholder="Field value"></StInput>
            </StFormItem>
            <StFormItem label="Label xl" :filled="input" size="xl">
              <template #labelRight>Optional</template>
              <StInput v-model="input" placeholder="Field value"></StInput>
            </StFormItem>
            <StFormItem
              label="Label error"
              :filled="input"
              :error-message="['Error text']"
            >
              <template #labelRight>Optional</template>
              <StInput v-model="input" placeholder="Field value">
                <svg
                  width="18"
                  height="18"
                  viewBox="0 0 18 18"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M12 13H18M14 9H18"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                  <circle
                    cx="8"
                    cy="5"
                    r="4"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                  <path
                    d="M8.3125 9C5.0625 9 9.9375 9 6.6875 9C3.4375 9 1 11.4 1 13.8C1 16.2 1 17 1 17H18"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                </svg>
                <svg
                  width="18"
                  height="18"
                  viewBox="0 0 18 18"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M7 7H1V1H7V7Z"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M11 0V3H14V1H17V5"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M7 18V16H4V17H1V14"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M11 18V16H14V17H17V14"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path d="M11 13H7V11H4" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M10 7H18" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M14 9V11H17V9" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M1 10V12" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M11 9V10.6364" stroke="#6B2AF7" stroke-width="2" />
                </svg>
              </StInput>
              <template #description>
                <p>Description/help text</p>
                <p>Description/help text</p>
              </template>
            </StFormItem>
            <StFormItem label="Label disabled" disabled :filled="input">
              <template #labelRight>Optional</template>
              <StInput v-model="input" disabled placeholder="Field value">
                <svg
                  width="18"
                  height="18"
                  viewBox="0 0 18 18"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M12 13H18M14 9H18"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                  <circle
                    cx="8"
                    cy="5"
                    r="4"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                  <path
                    d="M8.3125 9C5.0625 9 9.9375 9 6.6875 9C3.4375 9 1 11.4 1 13.8C1 16.2 1 17 1 17H18"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                </svg>
                <svg
                  width="18"
                  height="18"
                  viewBox="0 0 18 18"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M7 7H1V1H7V7Z"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M11 0V3H14V1H17V5"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M7 18V16H4V17H1V14"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M11 18V16H14V17H17V14"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path d="M11 13H7V11H4" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M10 7H18" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M14 9V11H17V9" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M1 10V12" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M11 9V10.6364" stroke="#6B2AF7" stroke-width="2" />
                </svg>
              </StInput>
              <template #description>
                <p>Description/help text</p>
                <p>Description/help text</p>
              </template>
            </StFormItem>
            <StFormItem label="Label readonly" readonly :filled="input">
              <template #labelRight>Optional</template>
              <StInput v-model="input" readonly placeholder="Field value">
                <svg
                  width="18"
                  height="18"
                  viewBox="0 0 18 18"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M12 13H18M14 9H18"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                  <circle
                    cx="8"
                    cy="5"
                    r="4"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                  <path
                    d="M8.3125 9C5.0625 9 9.9375 9 6.6875 9C3.4375 9 1 11.4 1 13.8C1 16.2 1 17 1 17H18"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                </svg>
                <svg
                  width="18"
                  height="18"
                  viewBox="0 0 18 18"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M7 7H1V1H7V7Z"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M11 0V3H14V1H17V5"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M7 18V16H4V17H1V14"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M11 18V16H14V17H17V14"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path d="M11 13H7V11H4" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M10 7H18" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M14 9V11H17V9" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M1 10V12" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M11 9V10.6364" stroke="#6B2AF7" stroke-width="2" />
                </svg>
              </StInput>
              <template #description>
                <p>Description/help text</p>
                <p>Description/help text</p>
              </template>
            </StFormItem>
            <StFormItem label="Label center" position="center" :filled="input">
              <StInput v-model="input" placeholder="Field value">
                <svg
                  width="18"
                  height="18"
                  viewBox="0 0 18 18"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M12 13H18M14 9H18"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                  <circle
                    cx="8"
                    cy="5"
                    r="4"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                  <path
                    d="M8.3125 9C5.0625 9 9.9375 9 6.6875 9C3.4375 9 1 11.4 1 13.8C1 16.2 1 17 1 17H18"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                </svg>
                <svg
                  width="18"
                  height="18"
                  viewBox="0 0 18 18"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M7 7H1V1H7V7Z"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M11 0V3H14V1H17V5"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M7 18V16H4V17H1V14"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M11 18V16H14V17H17V14"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path d="M11 13H7V11H4" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M10 7H18" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M14 9V11H17V9" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M1 10V12" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M11 9V10.6364" stroke="#6B2AF7" stroke-width="2" />
                </svg>
              </StInput>
              <template #description>
                <p>Description/help text</p>
                <p>Description/help text</p>
              </template>
            </StFormItem>
            <StFormItem label="Label md" :filled="amount" size="md">
              <template #labelRight>Optional</template>
              <StAmount v-model="amount" placeholder="Field value"></StAmount>
            </StFormItem>
          </div>
          <div class="dark grid">
            <StFormItem label="Label sm" color="dark" :filled="input">
              <template #labelRight>Optional</template>
              <StInput v-model="input" placeholder="Field value">
                <svg
                  width="18"
                  height="18"
                  viewBox="0 0 18 18"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M12 13H18M14 9H18"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                  <circle
                    cx="8"
                    cy="5"
                    r="4"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                  <path
                    d="M8.3125 9C5.0625 9 9.9375 9 6.6875 9C3.4375 9 1 11.4 1 13.8C1 16.2 1 17 1 17H18"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                </svg>
                <svg
                  width="18"
                  height="18"
                  viewBox="0 0 18 18"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M7 7H1V1H7V7Z"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M11 0V3H14V1H17V5"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M7 18V16H4V17H1V14"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M11 18V16H14V17H17V14"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path d="M11 13H7V11H4" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M10 7H18" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M14 9V11H17V9" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M1 10V12" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M11 9V10.6364" stroke="#6B2AF7" stroke-width="2" />
                </svg>
              </StInput>
              <template #description>
                <p>Description/help text</p>
                <p>Description/help text</p>
              </template>
            </StFormItem>
            <StFormItem label="Label md" :filled="input" color="dark" size="md">
              <template #labelRight>Optional</template>
              <StInput v-model="input" placeholder="Field value"></StInput>
            </StFormItem>
            <StFormItem label="Label lg" :filled="input" color="dark" size="lg">
              <template #labelRight>Optional</template>
              <StInput v-model="input" placeholder="Field value"></StInput>
            </StFormItem>
            <StFormItem label="Label xl" :filled="input" color="dark" size="xl">
              <template #labelRight>Optional</template>
              <StInput v-model="input" placeholder="Field value"></StInput>
            </StFormItem>
            <StFormItem
              label="Label error"
              color="dark"
              :filled="input"
              :error-message="error"
            >
              <template #labelRight>Optional</template>
              <StInput v-model="input" placeholder="Field value">
                <svg
                  width="18"
                  height="18"
                  viewBox="0 0 18 18"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M12 13H18M14 9H18"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                  <circle
                    cx="8"
                    cy="5"
                    r="4"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                  <path
                    d="M8.3125 9C5.0625 9 9.9375 9 6.6875 9C3.4375 9 1 11.4 1 13.8C1 16.2 1 17 1 17H18"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                </svg>
                <svg
                  width="18"
                  height="18"
                  viewBox="0 0 18 18"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M7 7H1V1H7V7Z"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M11 0V3H14V1H17V5"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M7 18V16H4V17H1V14"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M11 18V16H14V17H17V14"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path d="M11 13H7V11H4" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M10 7H18" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M14 9V11H17V9" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M1 10V12" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M11 9V10.6364" stroke="#6B2AF7" stroke-width="2" />
                </svg>
              </StInput>
              <template #description>
                <p>Description/help text</p>
                <p>Description/help text</p>
              </template>
            </StFormItem>
            <StFormItem
              label="Label disabled"
              color="dark"
              disabled
              :filled="input"
            >
              <template #labelRight>Optional</template>
              <StInput v-model="input" disabled placeholder="Field value">
                <svg
                  width="18"
                  height="18"
                  viewBox="0 0 18 18"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M12 13H18M14 9H18"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                  <circle
                    cx="8"
                    cy="5"
                    r="4"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                  <path
                    d="M8.3125 9C5.0625 9 9.9375 9 6.6875 9C3.4375 9 1 11.4 1 13.8C1 16.2 1 17 1 17H18"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                </svg>
                <svg
                  width="18"
                  height="18"
                  viewBox="0 0 18 18"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M7 7H1V1H7V7Z"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M11 0V3H14V1H17V5"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M7 18V16H4V17H1V14"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M11 18V16H14V17H17V14"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path d="M11 13H7V11H4" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M10 7H18" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M14 9V11H17V9" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M1 10V12" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M11 9V10.6364" stroke="#6B2AF7" stroke-width="2" />
                </svg>
              </StInput>
              <template #description>
                <p>Description/help text</p>
                <p>Description/help text</p>
              </template>
            </StFormItem>
            <StFormItem
              label="Label readonly"
              color="dark"
              readonly
              :filled="input"
            >
              <template #labelRight>Optional</template>
              <StInput v-model="input" readonly placeholder="Field value">
                <svg
                  width="18"
                  height="18"
                  viewBox="0 0 18 18"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M12 13H18M14 9H18"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                  <circle
                    cx="8"
                    cy="5"
                    r="4"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                  <path
                    d="M8.3125 9C5.0625 9 9.9375 9 6.6875 9C3.4375 9 1 11.4 1 13.8C1 16.2 1 17 1 17H18"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                </svg>
                <svg
                  width="18"
                  height="18"
                  viewBox="0 0 18 18"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M7 7H1V1H7V7Z"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M11 0V3H14V1H17V5"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M7 18V16H4V17H1V14"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M11 18V16H14V17H17V14"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path d="M11 13H7V11H4" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M10 7H18" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M14 9V11H17V9" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M1 10V12" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M11 9V10.6364" stroke="#6B2AF7" stroke-width="2" />
                </svg>
              </StInput>
              <template #description>
                <p>Description/help text</p>
                <p>Description/help text</p>
              </template>
            </StFormItem>
            <StFormItem
              label="Label center"
              position="center"
              color="dark"
              :filled="input"
            >
              <StInput v-model="input" placeholder="Field value">
                <svg
                  width="18"
                  height="18"
                  viewBox="0 0 18 18"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M12 13H18M14 9H18"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                  <circle
                    cx="8"
                    cy="5"
                    r="4"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                  <path
                    d="M8.3125 9C5.0625 9 9.9375 9 6.6875 9C3.4375 9 1 11.4 1 13.8C1 16.2 1 17 1 17H18"
                    stroke="#E5E4E8"
                    stroke-width="2"
                  />
                </svg>
                <svg
                  width="18"
                  height="18"
                  viewBox="0 0 18 18"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M7 7H1V1H7V7Z"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M11 0V3H14V1H17V5"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M7 18V16H4V17H1V14"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path
                    d="M11 18V16H14V17H17V14"
                    stroke="#6B2AF7"
                    stroke-width="2"
                  />
                  <path d="M11 13H7V11H4" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M10 7H18" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M14 9V11H17V9" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M1 10V12" stroke="#6B2AF7" stroke-width="2" />
                  <path d="M11 9V10.6364" stroke="#6B2AF7" stroke-width="2" />
                </svg>
              </StInput>
              <template #description>
                <p>Description/help text</p>
                <p>Description/help text</p>
              </template>
            </StFormItem>
            <StFormItem
              label="Label md"
              :filled="amount"
              color="dark"
              size="lg"
            >
              <template #labelRight>Optional</template>
              <StAmount v-model="amount" placeholder="Field value"></StAmount>
            </StFormItem>
          </div>
        </div>
      </template>
      <template v-if="activeTab === 'button'">
        <h1>Buttons</h1>
        <div class="light">
          <h2>Type A</h2>
          <div class="button-grid">
            <StButton size="large">Send</StButton>
            <StButton size="medium">Send</StButton>
            <StButton>Send</StButton>
            <StButton size="small">Send</StButton>
            <StButton size="xsmall">Send</StButton>
          </div>
          <div class="button-grid">
            <StButton disabled size="large">Send</StButton>
            <StButton disabled size="medium">Send</StButton>
            <StButton disabled>Send</StButton>
            <StButton disabled size="small">Send</StButton>
            <StButton disabled size="xsmall">Send</StButton>
          </div>
          <h2>Type B</h2>
          <div class="button-grid">
            <StButton type="type-b" size="large">Send</StButton>
            <StButton type="type-b" size="medium">Send</StButton>
            <StButton type="type-b">Send</StButton>
            <StButton type="type-b" size="small">Send</StButton>
            <StButton type="type-b" size="xsmall">Send</StButton>
          </div>
          <div class="button-grid">
            <StButton disabled type="type-b" size="large">Send</StButton>
            <StButton disabled type="type-b" size="medium">Send</StButton>
            <StButton disabled type="type-b">Send</StButton>
            <StButton disabled type="type-b" size="small">Send</StButton>
            <StButton disabled type="type-b" size="xsmall">Send</StButton>
          </div>
          <h2>Type C</h2>
          <div class="button-grid">
            <StButton type="type-c" size="large">Send</StButton>
            <StButton type="type-c" size="medium">Send</StButton>
            <StButton type="type-c">Send</StButton>
            <StButton type="type-c" size="small">Send</StButton>
            <StButton type="type-c" size="xsmall">Send</StButton>
          </div>
          <div class="button-grid">
            <StButton disabled type="type-c" size="large">Send</StButton>
            <StButton disabled type="type-c" size="medium">Send</StButton>
            <StButton disabled type="type-c">Send</StButton>
            <StButton disabled type="type-c" size="small">Send</StButton>
            <StButton disabled type="type-c" size="xsmall">Send</StButton>
          </div>
          <h2>Type D</h2>
          <div class="button-grid">
            <StButton type="type-d" size="large">Send</StButton>
            <StButton type="type-d" size="medium">Send</StButton>
            <StButton type="type-d">Send</StButton>
            <StButton type="type-d" size="small">Send</StButton>
            <StButton type="type-d" size="xsmall">Send</StButton>
          </div>
          <div class="button-grid">
            <StButton disabled type="type-d" size="large">Send</StButton>
            <StButton disabled type="type-d" size="medium">Send</StButton>
            <StButton disabled type="type-d">Send</StButton>
            <StButton disabled type="type-d" size="small">Send</StButton>
            <StButton disabled type="type-d" size="xsmall">Send</StButton>
          </div>
        </div>
      </template>
      <template v-if="activeTab === 'checkbox'">
        <h1>Checkbox</h1>
      </template>
      <template v-if="activeTab === 'radio'">
        <h1>Radio</h1>
      </template>
      <template v-if="activeTab === 'tags'">
        <h1>Tags</h1>
      </template>
      <template v-if="activeTab === 'toggle'">
        <h1>Toggle</h1>
        <StSwitch theme="dark" type="thunder">Feeless</StSwitch>
      </template>
      <template v-if="activeTab === 'tooltip'">
        <h1>Tooltip</h1>
        <StTooltip tooltip="tooltip" position="right"
          >This tooltip - Horizontally centered</StTooltip
        >
        <br />
        <StTooltip tooltip="">This tooltip - Empty</StTooltip>
      </template>
    </div>
  </div>
</template>

<script>
import StFormItem from '@/components/StFormItem.vue'
import StInput from '@/components/StInput.vue'
import StAmount from '@/components/StAmount.vue'
import StButton from '@/components/StButton.vue'
import StSwitch from '@/components/StSwitch.vue'
import StTooltip from '@/components/StTooltip.vue'
import { ref } from 'vue'
export default {
  components: {
    StFormItem,
    StSwitch,
    StInput,
    StButton,
    StAmount,
    StTooltip
  },
  setup() {
    const activeTab = ref('input')

    /* INPUT */
    const input = ref('')
    const amount = ref(0)
    const error = ref('Haha')

    function changeTab(tab) {
      activeTab.value = tab
    }

    return {
      activeTab,

      input,
      amount,
      error,

      changeTab
    }
  }
}
</script>

<style scoped>
.ui-container .ui-container__inner {
  padding: 20px;
}
.tabs {
  display: grid;
  grid-template-columns: repeat(7, 1.7fr);
}
.tabs-link {
  text-align: center;
  cursor: pointer;
  text-transform: uppercase;
  padding: 15px 20px;
  background-color: var(--grey100);
  color: var(--grey1000);
  font-weight: 600;
  transition: 0.3s;
}
.tabs-link:hover {
  background-color: var(--marine500);
  color: var(--white);
}
.tabs-link__active {
  background-color: var(--marine500);
  color: var(--white);
}
.dark,
.light {
  padding: 20px;
}
.dark {
  background-color: var(--marine900);
}
.grid {
  display: grid;
  grid-template-columns: repeat(4, 3fr);
  grid-gap: 80px;
}
.light h2 {
  margin: 20px 0;
}
.button-grid {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
}
.button-grid + .button-grid {
  margin-top: 40px;
}
</style>
