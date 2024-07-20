<script setup>
import { ref } from 'vue'

const price = ref(0)
const volume = ref(0)
const result = ref(0)

const handleCount = () => {
  const CONVERT_ML = 1000
  result.value = (price.value * CONVERT_ML) / volume.value
  if (!result.value) {
    result.value = 0
  }
}
</script>

<template>
  <header>
    <h1>Beer</h1>
    <h1>calculator</h1>
  </header>

  <main>
    <div class="form">
      <form>
        <div class="input-container">
          <label for="volume">Volume em ml </label>
          <input type="number" name="volume" id="volume" min="0" v-model="volume" />
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
header {
  text-align: center;
}

h1 {
  font-family: 'Monofett', monospace;
  font-weight: 400;
  font-size: 40px;
}

main {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 10px;
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
  height: 27px;
  box-shadow: 2px 2px gray;
  text-align: center;
  font-size: medium;
}

button {
  margin: 15px;
  width: 50%;
  height: 35px;
  border-radius: 50px;
  box-shadow: 5px 5px gray;
  align-self: center;
  font-family: 'Courier New', Courier, monospace;
  font-size: larger;
}
</style>
