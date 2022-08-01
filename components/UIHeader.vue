<script setup>
import { ref, defineEmits } from "vue";
// Components
import UIModal from "./UIModal";

const emit = defineEmits(["create"]);

const isOpened = ref(false);

function createTask(taskName) {
  emit("create", taskName);

  isOpened.value = false;
}
</script>

<template>
  <section class="header">
    <span class="header__title">
      To do list
    </span>

    <button @click="isOpened = true" class="header__button-add">
      +
    </button>

    <UIModal
      v-if="isOpened"
      @close="isOpened = false"
      @create="createTask"
    />
  </section>
</template>

<style lang="scss">
.header {
  display: flex;
  justify-content: space-between;
  flex: 1 1 0;

  padding: 104px 150px 0 150px;

  &__title {
    font-family: "Montserrat", serif;
    color: #16191D;

    font-weight: 700;
    font-size: 24px;
    line-height: 132%;
  }

  &__button-add {
    width: 40px;
    height: 40px;

    border-radius: 50%;

    border: none;
    background: #D6DBEB;

    font-size: 35px;
    font-weight: 200;
    color: #314B99;

    cursor: pointer;
  }
}
</style>
