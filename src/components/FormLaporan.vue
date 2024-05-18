<template>
    <div class="form-container">
      <div class="form-card">
        <h2>Tambah Laporan</h2>
        <form @submit.prevent="kirimLaporan">
          <div class="form-group">
            <label for="judul">Judul:</label>
            <input type="text" v-model="judul" id="judul" required>
          </div>
          <div class="form-group">
            <label for="deskripsi">Deskripsi:</label>
            <textarea v-model="deskripsi" id="deskripsi" required></textarea>
          </div>
          <button type="submit">Kirim</button>
        </form>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const judul = ref('');
  const deskripsi = ref('');
  
  const kirimLaporan = () => {
    const laporanBaru = {
      judul: judul.value,
      deskripsi: deskripsi.value
    };
    judul.value = '';
    deskripsi.value = '';
    emit('tambah-laporan', laporanBaru);
  };
  
  const emit = defineEmits(['tambah-laporan']);
  </script>
  
  <style scoped>
  .form-container {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
  }
  
  .form-card {
    background-color: #fff;
    border-radius: 20px;
    padding: 20px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    width: 300px;
  }
  
  h2 {
    text-align: center;
    margin-bottom: 20px;
  }
  
  .form-group {
    display: flex;
    flex-direction: column;
    gap: 5px;
    margin-bottom: 15px;
  }
  
  form {
    display: flex;
    flex-direction: column;
    gap: 10px;
  }
  
  button {
    align-self: center;
    padding: 10px 20px;
    border: none;
    background-color: #007bff;
    color: white;
    border-radius: 5px;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #0056b3;
  }
  </style>
  