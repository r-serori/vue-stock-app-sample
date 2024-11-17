<template>
  <div class="box-container">
    <div class="top-bar">
      <SearchBarComponent @search="handleSearch" />
      <AddNewItemButton @add="handleAddNewItem" />
    </div>
    <TableComponent :data="filteredItems" />
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import SearchBarComponent from "./SearchBarComponent.vue";
import AddNewItemButton from "./AddNewItemButton.vue";
import TableComponent from "./TableComponent.vue";

// アイテムの型定義
interface Item {
  name: string;
  price: number;
  inStock: boolean;
}

// アイテムリスト
const items = ref<Item[]>([
  { name: "商品A", price: 1000, inStock: true },
  { name: "商品B", price: 1500, inStock: false },
  { name: "商品C", price: 2000, inStock: true },
]);

// フィルタリングされたアイテム
const filteredItems = ref<Item[]>([...items.value]);

// 新規登録ボタンのハンドラー
const handleAddNewItem = (): void => {
  alert("新規登録画面へ移動します。");
};

// 検索処理
const handleSearch = (searchTerm: string): void => {
  filteredItems.value = items.value.filter((item) =>
    item.name.includes(searchTerm)
  );
};
</script>

<style>
</style>
