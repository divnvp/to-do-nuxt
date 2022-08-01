<script setup>
import { defineProps } from "vue";

defineProps({
  record: { type: Object, required: true }
});
</script>

<template>
  <div class="tr-row">
    <div class="tr-col">
      <input type="checkbox" class="checkbox-circle">
    </div>

    <div class="tr-col name">
      <span>
        {{ record.name }}
      </span>
    </div>

    <div class="tr-col status">
      <span
        :style="{ color: record.status == 'Выполнено' ? '#134EC1' : '#F89B11' }"
      >
        {{ record.status }}
      </span>
    </div>

    <div class="tr-col date">
      <span>
        {{ new Date(record.date).toLocaleDateString() }}
      </span>
    </div>
  </div>
</template>

<style lang="scss">
.tr {
  &-row {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;

    padding: 17px 40px;

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

  &-col {
    display: flex;
    flex-direction: column;
    flex: 1;

    padding-right: 41px;
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

    display: flex;
    justify-content: center;
    align-items: center;

    margin-top: 2px;

    outline: none;
    border: none;
  }
}

.name {
  span {
    width: 900px;
  }
}

.status {
  margin-left: -47px;

  span {
    width: 151px;
  }
}

.date {
  margin-left: -17px;

  span {
    width: 129px;
  }
}
</style>
