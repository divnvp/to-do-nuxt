<script setup>
import { ref } from "vue";
// Components
import UIHeader from './UIHeader.vue';
import UIMain from './UIMain.vue';

const records = ref([
  { name: "Размещение новостей на сайте", status: "Выполнено", date: "22.04.2022" },
  { name: "Внедрить Wi-fi для читателей", status: "В работе", date: "22.04.2022" },
  { name: "Отредактировать раздел “Доступная среда”", status: "Выполнено", date: "22.04.2022" },
  { name: "Презентация “Информационные технологии”", status: "В работе", date: "22.04.2022" },
  { name: "Счётчики — внедрить дизайн", status: "В работе", date: "22.04.2022" },
  { name: "Сверстать новый layout", status: "В работе", date: "22.04.2022" },
  { name: "Скролл в новостях", status: "Выполнено", date: "22.04.2022" },
  { name: "Форма сброса пароля", status: "В работе", date: "22.04.2022" },
  { name: "Внедрение модуля Chat", status: "Выполнено", date: "22.04.2022" }
]);

function createTask(taskName) {
  records.value.unshift({
    name: taskName,
    status: "В работе",
    date: new Date().toLocaleDateString()
  });
}
</script>

<template>
  <div>
    <header class="margin-left">
      <UIHeader @create="createTask" />
    </header>

    <main>
      <UIMain :records="records" />
    </main>
  </div>
</template>

<style lang="scss">
.margin-left {
  margin-left: 40px;
}
</style>
