<script setup>
import TableRow from './TableRow.vue';

const records = [
  { id: 1, name: "Размещение новостей на сайте", status: "Выполнено", date: "22.04.2022" },
  { id: 2, name: "Внедрить Wi-fi для читателей", status: "В работе", date: "22.04.2022" },
  { id: 3, name: "Отредактировать раздел “Доступная среда”", status: "Выполнено", date: "22.04.2022" },
  { id: 4, name: "Презентация “Информационные технологии”", status: "В работе", date: "22.04.2022" },
  { id: 5, name: "Счётчики — внедрить дизайн", status: "В работе", date: "22.04.2022" },
  { id: 6, name: "Сверстать новый layout", status: "В работе", date: "22.04.2022" },
  { id: 7, name: "Скролл в новостях", status: "Выполнено", date: "22.04.2022" },
  { id: 8, name: "Форма сброса пароля", status: "В работе", date: "22.04.2022" },
  { id: 9, name: "Внедрение модуля Chat", status: "Выполнено", date: "22.04.2022" }
]
</script>

<template>
  <section>
    <header class="table-header">
      <aside class="table-header__name">
        <hr />
        <span>Описание</span>
      </aside>
      
      <aside class="table-header__name" style="margin-left: 58%">
        <hr />
        <span>Статус</span>
      </aside>

      <aside class="table-header__name" style="margin-right: 6%">
        <hr />
        <span>Дата</span>
      </aside>
    </header>

    <div class="table-body">
      <TableRow
        v-for="record in records"
        :key="record.id"
        :record="record"
      />
    </div>
  </section>
</template>

<style lang="scss">
header {
  display: flex;
}

.col {
  display: flex;
  flex: 1;
}

.table {
  font-family: "VelaSans", sans-serif;
  font-weight: 400;
  font-size: 14px;
  line-height: 132%;
  color: #16191D;

  hr {
    padding: 0;
    margin-right: 20px;

    width: 1px;
    height: 32px;

    border: none;
    border-left: 1px solid #C4C4C4;
  }

  &-row {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: flex-start;
  }

  &-header {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    flex: 1 1 0;

    margin-bottom: 17px;
    margin-left: 100px;

    font-family: "VelaSans", sans-serif;
    font-weight: 400;
    font-size: 14px;
    line-height: 132%;

    &__name {
      display: flex;
      flex-direction: row;
      align-items: center;
      justify-content: flex-start;
    }

    hr {
      padding: 0;
      margin-right: 20px;

      width: 1px;
      height: 32px;

      border: none;
      border-left: 1px solid #C4C4C4;
    }
  }

  &-body {
    display: flex;
    flex-direction: column;
    justify-content: center;
    flex: 1 1 0;
  }
}
</style>
