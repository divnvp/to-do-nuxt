<script setup>
import UISearch from './UISearch.vue';
import UISort from './UISort.vue';

</script>

<template>
  <section class="list-actions">
    <UISearch />

    <UISort />
  </section>
</template>

<style lang="scss">
.list-actions {
  display: flex;
  justify-content: space-between;
  flex: 1 1 0;

  margin-top: 34px;
}
</style>
