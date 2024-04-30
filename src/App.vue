<template>
  <div>
    <div class="note">
      <h1>Заметка</h1>
      <input type="text" v-model="controller" @keyup.enter="addText">
      <button @click="addText">Добавить заметку</button>
      <ul>
        <li v-for="(item, index) in textList" :key="index">
          {{ item }}
          <button @click="removeText(index)">Удалить заметку</button>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

let controller = ref('');
let textList = ref([]);

function addText() {
  textList.value.push(controller.value);
  controller.value = '';
}

function removeText(index) {
  textList.value.splice(index, 1);
}
</script>

<style>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
li {
  list-style: decimal;
}
.note h1{
  text-align: center;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  font-size: 40px;
}
.note{
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>

// Написать Простое приложение с добавление Заметок через composition API до 2
мая 2024 года
