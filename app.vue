<template>
  <div class="container">
    <h1>Counter APP</h1>
    <div>
      <input v-model="nama" placeholder="Masukkan Nama" type="text">
      <button @click="submitNama">submit</button>
    </div>

    <div v-if="submitted">
      <h1>Halo {{ nama }} silakan jalankan conter</h1>
      <div>
        <h1 :style="{ color: warna}">{{ counter }}</h1>
        <button @click="kurang">-</button>
        <button @click="tambah">+</button>
      </div>
    </div>


  </div>
</template>

<script setup lang="js">
import { ref, computed } from "vue";

const nama = ref("");
const submitted = ref(false);
const counter = ref(0);


const warna = computed(() => (counter.value % 2 === 0 ? "red" : "blue"));

const submitNama = () => {
  if (nama.value.trim()) submitted.value = true;
};

const tambah = () => counter.value++;
const kurang = () => counter.value--;
</script>

<style>
.container {
  text-align: start;
  margin-top: 50px;
}

button {
  margin: 3px;
  padding: 3px;
  font-size: 15px;
  cursor: pointer;
}

input{
  margin: 5px;
  padding: 3px;
  font-size: 15px;
}
</style>
