<script setup>
import { ref } from "vue";
// Components
import UIHeader from './UIHeader.vue';
import UIMain from './UIMain.vue';

const records = ref(JSON.parse(localStorage.getItem("records")) || [
  { name: "Размещение новостей на сайте", status: "Выполнено", date: new Date("2022-04-22") },
  { name: "Внедрить Wi-fi для читателей", status: "В работе", date: new Date("2022-04-22") },
  { name: "Отредактировать раздел “Доступная среда”", status: "Выполнено", date: new Date("2022-04-22") },
  { name: "Презентация “Информационные технологии”", status: "В работе", date: new Date("2022-04-22") },
  { name: "Счётчики — внедрить дизайн", status: "В работе", date: new Date("2022-04-22") },
  { name: "Сверстать новый layout", status: "В работе", date: new Date("2022-04-22") },
  { name: "Скролл в новостях", status: "Выполнено", date: new Date("2022-04-22") },
  { name: "Форма сброса пароля", status: "В работе", date: new Date("2022-04-22") },
  { name: "Внедрение модуля Chat", status: "Выполнено", date: new Date("2022-04-22") }
]);

function createTask(taskName) {
  records.value.unshift({
    name: taskName,
    status: "В работе",
    date: new Date()
  });

  localStorage.setItem("records", JSON.stringify(records.value));
}

function sortRecords(by) {
  if (by === "date") {
    records.value = records.value.sort((a, b) => {
      const aToDate = new Date(a.date);
      const bToDate = new Date(b.date);

      if (aToDate.getTime() > bToDate.getTime()) {
        return 1;
      }
      if (aToDate.getTime() < bToDate.getTime()) {
        return -1;
      }
      return 0;
    });
  } else if (by === "status") {
    records.value = records.value.sort((a, b) => {
      if (a.status > b.status) {
        return 1;
      }
      if (a.status < b.status) {
        return -1;
      }
      return 0;
    });
  } else {
    records.value = JSON.parse(localStorage.getItem("records"));
  }
}

function searchRecord(value) {
  records.value = JSON.parse(localStorage.getItem("records"));

  if (value) {
    records.value = records.value.filter((record, index) => index + 1 == value ||
      record.name.includes(value) ||
      record.status.includes(value) ||
      new Date(record.date).toLocaleDateString().includes(value)
    );
  }
}
</script>

<template>
  <div>
    <header class="margin-left">
      <UIHeader @create="createTask" />
    </header>

    <main>
      <UIMain
        :records="records"
        @sort="sortRecords"
        @search="searchRecord"
      />
    </main>
  </div>
</template>

<style lang="scss">
.margin-left {
  margin-left: 40px;
}
</style>
