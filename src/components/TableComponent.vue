<template>
  <table>
    <thead>
      <tr>
        <th>商品名</th>
        <th>価格</th>
        <th>在庫状況</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(item, index) in data" :key="index">
        <td>{{ item.name }}</td>
        <td>{{ item.price }}</td>
        <td>{{ item.inStock ? "在庫あり" : "在庫なし" }}</td>
      </tr>
    </tbody>
  </table>
</template>

<script setup>
import { defineProps } from "vue";

// テーブルデータのプロパティを受け取る
const props = defineProps({
  data: {
    type: Array,
    required: true,
  },
});
</script>

<style>
</style>
