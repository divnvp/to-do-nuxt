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
}

.search__input {
  margin-left: 16px;
  min-width: 227px;

  border: none;
}

.search__input:focus {
  outline: none;
}
</style>