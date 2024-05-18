<template>
    <div class="item-laporan">
      <h3>{{ laporan.judul }}</h3>
      <p>{{ laporan.deskripsi }}</p>
    </div>
  </template>
  
  <script setup>
  const props = defineProps({
    laporan: Object
  });
  </script>
  
  <style scoped>
  .item-laporan {
    border: 1px solid #ccc;
    padding: 10px;
    margin: 10px 0;
  }
  </style>
  