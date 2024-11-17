<template>
  <div class="box-container">
    <div class="top-bar">
      <SearchBarComponent @search="handleSearch" />
      <AddNewItemButton @add="handleAddNewItem" />
    </div>
    <TableComponent :data="filteredItems" />
  </div>
</template>

<script setup>
import { ref } from "vue";
import SearchBarComponent from "./SearchBarComponent.vue";
import AddNewItemButton from "./AddNewItemButton.vue";
import TableComponent from "./TableComponent.vue";

// アイテムリストを定義
const items = ref([
  { name: "商品A", price: 1000, inStock: true },
  { name: "商品B", price: 1500, inStock: false },
  { name: "商品C", price: 2000, inStock: true },
]);

// フィルタリングされたアイテムを管理
const filteredItems = ref([...items.value]);

// 新規登録ボタンのハンドラー
const handleAddNewItem = () => {
  alert("新規登録画面へ移動します。");
};

// 検索処理
const handleSearch = (searchTerm) => {
  filteredItems.value = items.value.filter((item) =>
    item.name.includes(searchTerm)
  );
};
</script>

<style>
</style>
