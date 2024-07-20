<script setup>
import { ref } from 'vue'

const price = ref(0)
const volume = ref(0)
const result = ref(0)

const handleCount = () => {
  const CONVERT_ML = 1000
  result.value = (price.value * CONVERT_ML) / volume.value
}
</script>

<template>
  <header>
    <h1>Beer calculator</h1>
  </header>

  <main>
    <div class="form">
      <form>
        <div class="input-container">
          <label for="volume">Volume em ml </label>
          <input type="number" name="volume" id="volume" v-model="volume" />
        </div>
        <div class="input-container">
          <label for="price">Preço </label>
          <input type="number" name="price" id="price" min="0" step="0.01" v-model="price" />
        </div>
      </form>
      <button @click="handleCount">Go</button>
    </div>
    <div class="result">
      <h2>R$ {{ result.toFixed(2).toString().replace('.', ',') }} por litro</h2>
    </div>
  </main>
</template>

<style scoped>
main {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.input-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 5px;
  padding: 7px;
}

.form {
  display: flex;
  flex-direction: column;
  margin: 5px;
  gap: 10px;
}

input {
  border-radius: 10px;
  height: 25px;
  box-shadow: 2px 2px gray;
}

button {
  margin-bottom: 10px;
  width: 50%;
  height: 30px;
  border-radius: 50px;
  box-shadow: 5px 5px gray;
  align-self: center;
}
</style>
