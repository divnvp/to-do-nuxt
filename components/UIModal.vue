<script setup>
import {defineEmits, ref} from "vue";

defineEmits(["close", "create"]);

const newTask = ref("");
</script>

<template>
  <section class="modal__container">
    <div class="modal__window">
      <div class="row">
        <span class="window__title">
          Создать новую задачу
        </span>

        <button @click="$emit('close')" class="window__button_close">
          <img src="../static/close.png">
        </button>
      </div>

      <div class="row">
        <span class="window__description">
          Описание
        </span>
      </div>

      <div class="row">
        <input
          v-model="newTask"
          type="text"
          placeholder="Введите описание"
          class="window__input"
        >
      </div>

      <div class="create">
        <button
          @click="$emit('create', newTask)"
          class="window__button_create"
        >
          Создать
        </button>
      </div>
    </div>
  </section>
</template>

<style scoped>
.modal__container {
  position: fixed;
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;

  display: flex;
  flex-flow: column nowrap;
  justify-content: center;
  align-items: center;

  z-index: 99;

  backdrop-filter: blur(4px);
}

.modal__window {
  background: #FFFFFF;
  border: 1px solid #DDE2E4;

  box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.25);
  border-radius: 6px;

  padding: 40px;

  transition: transform 0.15s ease 0s, opacity 0.15s ease 0s;
  transform: scale(1);

  font-family: 'Montserrat', serif;
}

.window__title {
  font-weight: 700;

  font-size: 18px;
  line-height: 132%;

  color: #16191D;

  margin-bottom: 30px;
  margin-right: 62px;
}

.window__button_close {
  display: flex;
  align-items: center;
  justify-content: center;

  width: 22px;
  height: 22px;

  background: #314B99;
  border-radius: 5px;
  border: none;
}

.window__button_close img {
  width: 6px;
  height: 6px;
}

.window__description {
  font-size: 14px;
  line-height: 14px;

  margin-bottom: 5px;
}

.window__input {
  background: #FFFFFF;
  border: 1px solid #DDE2E4;
  border-radius: 8px;

  padding: 11px 16px;

  width: 100%;

  margin-bottom: 30px;

  font-weight: 400;
  font-size: 14px;
  line-height: 132%;

  color: #000000;
}

.window__input::placeholder {
  font-weight: 400;
  font-size: 14px;
  line-height: 132%;

  color: #000000;

  opacity: 0.5;
}

.window__button_create {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;

  padding: 12px 40px;

  width: 153px;
  height: 48px;

  background: #F0F5FF;
  border-radius: 8px;
  border: none;

  font-weight: 400;
  font-size: 18px;
  line-height: 132%;

  color: #314B99;
}

.create {
  display: flex;
  flex-direction: row;
  width: 100%;
  justify-content: center;
}

.row {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
</style>
