<template>
  <div id="app">
    <calc-console query="12 x 12" total="144"></calc-console>
    <calc-keypad></calc-keypad>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import { injectGlobal } from 'vue-styled-components';

import CalcConsole from '@/components/CalcConsole.vue';
import CalcKeypad from '@/components/CalcKeypad.vue';

@Component({
  components: {
    CalcConsole,
    CalcKeypad,
  },
})
export default class App extends Vue {}

// Styles
injectGlobal`
	* {
	  font-family: 'Roboto', sans-serif;
    box-sizing: border-box;
	}

	body {
		margin: 0;
	}
`;
</script>
