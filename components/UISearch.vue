<script setup>
import { defineProps, defineEmits, computed } from "vue";

const props = defineProps({
  modelValue: String
});
const emit = defineEmits(["update:modelValue", "update"]);

const searchModel = computed({
  get() {
    return props.modelValue;
  },
  
  set(newValue) {
    emit("update", newValue);
  }
})
</script>

<template>
  <article class="search">
    <img src="../static/search.png">

    <input
      v-model="searchModel"
      placeholder="Поиск ID, Имени, статуса или даты"
      class="search__input"
    />
  </article>
</template>

<style lang="scss">
.search {
  display: flex;
  align-items: center;

  &__input {
    margin-left: 16px;
    min-width: 227px;

    border: none;
  }

  &__input:focus {
    outline: none;
  }
}

input::placeholder {
  font-weight: 400;
  font-size: 14px;
  line-height: 132%;

  color: #C4C4C4;
}
</style>