<template>
  <calc-keypad-styled>
    <calc-digit-buttons>
      <calc-digit-button v-for="button in digitButtons" :key="button">
        {{button}}
      </calc-digit-button>
    </calc-digit-buttons>
    <calc-action-buttons>
      <calc-action-button v-for="button in actionButtons" :key="button">
        <component v-bind:is="button" fillColor="red"></component>
      </calc-action-button>
    </calc-action-buttons>
  </calc-keypad-styled>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import styled from 'vue-styled-components';

import BackspaceIcon from "vue-material-design-icons/Backspace.vue";

const CalcKeypadStyled = styled.div`
  display: flex;
  height: 60vh;
  background: rgba(0,0,0,.06);
`;

const CalcDigitButtons = styled.div`
  display: flex;
  flex-wrap: wrap;
  width: 75%;
  border-right: 1px solid rgba(0,0,0,.2);;
`;

const CalcDigitButton = styled.button`
  width: 33%;
  font-size: 2em;
  height: 25%;
`;

const CalcActionButtons = styled.div`
  display: flex;
  flex-direction: column;
  width: 25%;
`;

const CalcActionButton = styled.button`
  font-size: 2em;
  height: 25%;
  width: 100%;
  color: royalblue;
`;

const CalcButtonContainer = styled.button`

`;

@Component({
  components: {
    CalcKeypadStyled,
    CalcDigitButtons,
    CalcDigitButton,
    CalcActionButtons,
    CalcActionButton,
    BackspaceIcon,
  }
})
export default class CalcKeypad extends Vue {
  digitButtons = ['7', '8', '9', '4', '5', '6', '1', '2', '3', '0', '.', '=']
  actionButtons = ['BackspaceIcon']
}
</script>
