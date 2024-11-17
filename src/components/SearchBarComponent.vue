<template>
  <div class="search-container">
    <label>商品名</label>
    <input type="text" v-model="searchTerm" placeholder="商品を検索" @input="onSearchInput" />
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import { defineEmits } from "vue";

// イベントの型定義
const emit = defineEmits<{
  (e: "search", term: string): void;
}>();

// 検索キーワード
const searchTerm = ref<string>("");

// 検索イベントを送信
const onSearchInput = (): void => {
  emit("search", searchTerm.value);
};
</script>

<style>
</style>
