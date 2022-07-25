<script setup>

</script>

<template>
  <article class="sort">
    <span>Сортировать по:</span>

    <select class="sort__select">
      <optgroup>
        <option
          selected
        >
          Дата
        </option>
      </optgroup>
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