<template>
  <button @click="onAddClick" class="add-button">新規登録</button>
</template>

<script setup lang="ts">
import { defineEmits } from "vue";

// イベントの型定義
const emit = defineEmits<{
  (e: "add"): void;
}>();

// 新規登録イベントを送信
const onAddClick = (): void => {
  emit("add");
};
</script>

<style>
</style>
