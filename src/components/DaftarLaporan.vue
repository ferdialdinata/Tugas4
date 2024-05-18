<template>
    <div class="Data">
      <h2>Daftar Laporan</h2>
      <item-laporan v-for="(laporan, index) in laporan" :key="index" :laporan="laporan"></item-laporan>
    </div>
  </template>
  
  <script setup>
  import ItemLaporan from './ItemLaporan.vue';
  
  const props = defineProps({
    laporan: Array
  });
  </script>
  
<style scoped>
.Data {
    margin-top: -15%;
}
</style>