<script setup>
import { defineProps, defineEmits } from "vue";
// Components
import UISearch from './UISearch.vue';
import UISort from './UISort.vue';
import UITable from './table/UITable.vue';

defineProps({
  records: { type: Array, required: true }
});
const emit = defineEmits(["sort", "search"]);

function setSearchInput(value) {
  emit("search", value);
}

function sortRecords(sortBy) {
  emit("sort", sortBy);
}
</script>

<template>
  <section>
    <section class="list-actions">
      <UISearch
        @search="setSearchInput"
      />

      <UISort
        @sort="sortRecords"
      />
    </section>

    <section class="list-table">
      <UITable
        :records="records"
      />
    </section>
  </section>
</template>

<style lang="scss">
.list {
  &-actions {
    display: flex;
    justify-content: space-between;
    flex: 1 1 0;

    margin-top: 34px;
    margin-left: 40px;
  }

  &-table {
    margin-top: 30px;
  }
}
</style>
