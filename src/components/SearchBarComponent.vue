<template>
  <div class="search-container">
    <label>商品名</label>
    <input type="text" v-model="searchTerm" placeholder="商品を検索" @input="onSearchInput" />
  </div>
</template>

<script setup>
import { ref } from "vue";
import { defineEmits } from "vue";

// 親コンポーネントに検索用のイベントを送信
const emit = defineEmits(["search"]);
const searchTerm = ref("");

const onSearchInput = () => {
  emit("search", searchTerm.value);
};
</script>

<style>
</style>
