<script setup>
import UISearch from './UISearch.vue';
import UISort from './UISort.vue';
import UITable from './UITable.vue';

</script>

<template>
  <section>
    <section class="list-actions">
      <UISearch />

      <UISort />
    </section>

    <section class="list-table">
      <UITable />
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
