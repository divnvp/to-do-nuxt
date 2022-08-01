<script setup>
import { defineProps } from "vue";
import TableRow from './TableRow.vue';

defineProps({
  searching: String,
  records: { type: Array, required: true }
});

</script>

<template>
  <section>
    <header class="table-header">
      <aside class="table-header__name">
        <hr />
        <span>Описание</span>
      </aside>

      <aside class="table-header__name" style="margin-left: 58%">
        <hr />
        <span>Статус</span>
      </aside>

      <aside class="table-header__name" style="margin-right: 6%">
        <hr />
        <span>Дата</span>
      </aside>
    </header>

    <div class="table-body">
      <TableRow
        v-for="(record, index) in records"
        :key="index"
        :record="record"
      />
    </div>
  </section>
</template>

<style lang="scss">
header {
  display: flex;
}

.col {
  display: flex;
  flex: 1;
}

.table {
  font-family: "VelaSans", sans-serif;
  font-weight: 400;
  font-size: 14px;
  line-height: 132%;
  color: #16191D;

  hr {
    padding: 0;
    margin-right: 20px;

    width: 1px;
    height: 32px;

    border: none;
    border-left: 1px solid #C4C4C4;
  }

  &-row {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: flex-start;
  }

  &-header {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    flex: 1 1 0;

    margin-bottom: 17px;
    margin-left: 100px;

    font-family: "VelaSans", sans-serif;
    font-weight: 400;
    font-size: 14px;
    line-height: 132%;

    &__name {
      display: flex;
      flex-direction: row;
      align-items: center;
      justify-content: flex-start;
    }

    hr {
      padding: 0;
      margin-right: 20px;

      width: 1px;
      height: 32px;

      border: none;
      border-left: 1px solid #C4C4C4;
    }
  }

  &-body {
    display: flex;
    flex-direction: column;
    justify-content: center;
    flex: 1 1 0;
  }
}
</style>
