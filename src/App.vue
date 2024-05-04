<template>
  <div>
    <h1>Seberapa sayang kamu sama aku??</h1>
    <p>Masukkan biodata kamu</p>
    <form>
      <input type="text" v-model="namalengkap" placeholder="Tulis nama kamu disini"><br>
      <input type="angka" v-model="tanggallahirkamu" placeholder="Masukkan tanggal lahir"><br>
    </form><br>
    <p>Masukkan biodata pasangan kamu</p>
    <form>
      <input type="text" v-model="namalengkappasangan" placeholder="Tulis nama pasangan kamu disini"><br>
      <input type="angka" v-model="tanggallahirpasangan" placeholder="Masukkan tanggal lahir pasangan kamu"><br>
    </form>
    <button @click="hitungHasil">Lihat hasil</button>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const namalengkap = ref('')
const tanggallahirkamu = ref('')
const namalengkappasangan = ref('')
const tanggallahirpasangan = ref('')

function hitungHasil() {
  const hasil = (parseInt(tanggallahirkamu.value) + parseInt(tanggallahirpasangan.value)) % 2
  if (hasil === 0) {
    alert("Kalian cocok!")
  } else {
    alert("Kalian tidak cocok.")
  }
}
</script>

<style scoped>
p{
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}
.container {
  max-width: 400px;
  margin: 0 auto;
  text-align: center;
  padding: 20px;
  border: 1px solid #b60c0c;
  border-radius: 10px;
  background-color: #f9f9f9;
}

input {
  width: 100%;
  padding: 10px;
  margin-bottom: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

button {
  padding: 10px 20px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #0056b3;
}
</style>