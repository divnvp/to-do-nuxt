<script setup>
import { defineProps } from "vue";

defineProps({
  record: { type: Object, required: true }
});
</script>

<template>
  <div class="tr-row">
    <div class="tr-col" style="width: 100px;">
      <input type="checkbox" class="checkbox-circle">
    </div>

    <div class="tr-col">
      <span class="tr-col__record">
        {{ record.name }}
      </span>
    </div>
    
    <div class="tr-col">
      <span
        class="tr-col__status"
        :style="{ color: record.status == 'Выполнено' ? '#134EC1' : '#F89B11' }"
      >
        {{ record.status }}
      </span>
    </div>

    <div class="tr-col">
      <span>
        {{ record.date }}
      </span>
    </div>
  </div>
</template>

<style lang="scss">
.tr-row {
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;

  padding: 20px 40px;

  border-top: 1px solid #EEEBE9;
  border-bottom: 1px solid #EEEBE9;

  font-family: "VelaSans", sans-serif;
  font-weight: 400;
  font-size: 14px;
  line-height: 132%;

  &:hover {
    background: #F6F9FF;
  }

  &:hover input[type="checkbox"] {
    border: 1px solid #134EC1;
    box-shadow: 0px 4px 4px rgba(19, 78, 193, 0.15);
  }
}

.tr-col {
  display: flex;
  flex-direction: column;
  flex: 1;

  padding-right: 41px;

  &__record {
    width: calc(937px - 15px * 3 - 20px * 2);

    margin-left: 15px;
  }

  &__status {
    width: calc(151px - 15px);
  }
}

.checkbox-circle {
  width: 20px;
  height: 20px;

  border-radius: 50%;

  border: 1px solid #16191D;

  vertical-align: middle;
  appearance: none;
  -webkit-appearance: none;
  outline: none;

  cursor: pointer;

  &:checked {
    border: 1px solid #134EC1;
    box-shadow: 0px 4px 4px rgba(19, 78, 193, 0.15);
  }

  &:checked:after {
    content: url("../../static/ok.png");
    margin-left: 3px;
    outline: none;
    border: none;
  }
} 
</style>
