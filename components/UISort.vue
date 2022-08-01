<script setup>
import { defineEmits, ref, watch } from "vue";

const emit = defineEmits(["sort"]);

const selectedSortBy = ref("Дата");

watch(selectedSortBy, (newValue) => {
  emit("sort", newValue);
})
</script>

<template>
  <article class="sort">
    <span>Сортировать по:</span>

    <select v-model="selectedSortBy" class="sort__select">
      <option value="default">(Нет)</option>
      <option
        value="date"
        selected
      >
        Дата
      </option>
      <option value="status">Статус</option>
    </select>
  </article>
</template>

<style lang="scss">
.sort {
  display: flex;
  align-items: center;
  justify-content: flex-end;

  font-family: "VelaSans", sans-serif;
  font-style: normal;
  font-weight: 400;
  font-size: 14px;

  &__select {
    font-weight: 400;
    font-size: 14px;

    margin-left: 15px;

    border: none;
  }
}

optgroup {
  font-weight: 400;
  font-size: 14px;
  line-height: 132%;
  color: #16191D;
}
</style>
