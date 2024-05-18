<template>
  <div id="app">
    <h1>Laporan Keresahan Masyarakat</h1>
    <form-laporan @tambah-laporan="tambahLaporan"></form-laporan>
    <daftar-laporan :laporan="laporan"></daftar-laporan>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import FormLaporan from './components/FormLaporan.vue';
import DaftarLaporan from './components/DaftarLaporan.vue';

const laporan = ref([]);

const tambahLaporan = (laporanBaru) => {
  laporan.value.push(laporanBaru);
};
</script>

<style scoped>
h1 {
  text-align: center;
}
</style>
