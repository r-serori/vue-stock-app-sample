<template>
  <button @click="onAddClick" class="add-button">新規登録</button>
</template>

<script setup>
import { defineEmits } from "vue";

// 新規登録イベントを送信
const emit = defineEmits(["add"]);

const onAddClick = () => {
  emit("add");
};
</script>

<style>
</style>
