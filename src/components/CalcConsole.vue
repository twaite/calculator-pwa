<template>
  <calc-console-styled>
    <calc-query-input :value="query">
    </calc-query-input>
    <calc-result-row>
      {{total}}
    </calc-result-row>
  </calc-console-styled>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import styled from 'vue-styled-components';

// TODO: consider moving to their own files?
const CalcConsoleStyled = styled.div`
  height: 40vh;
  padding: 2em;
  display: flex;
  flex-direction: column;
  justify-content: center;
  box-shadow: 0 1px 5px rgba(0,0,0,0.23);
`;

const CalcQueryInput = styled.input`
  text-align: right;
  font-weight: normal;
  font-size: 3em;
  margin-bottom: 0;
`;

const CalcResultRow = styled.h1`
  color: grey;
  text-align: right;
  font-weight: normal;
  font-size: 3em;
`;

@Component({
  components: {
    CalcQueryInput,
    CalcConsoleStyled,
    CalcResultRow
  },
  props: {
    query: String,
    total: String,
  },
})
export default class CalcConsole extends Vue { }
</script>
