<script setup>

</script>

<template>
  <section class="header">
    <span class="header__title">
      To do list
    </span>

    <button class="header__button-add">
      +
    </button>
  </section>
</template>

<style lang="scss">
.header {
  display: flex;
  justify-content: space-between;
  flex: 1 1 0;

  &__title {
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
