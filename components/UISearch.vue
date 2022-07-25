<script setup>

</script>

<template>
  <article class="search">
    <img src="../static/search.png">

    <input
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