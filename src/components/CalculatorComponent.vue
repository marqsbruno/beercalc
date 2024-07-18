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
    <div>
      <form>
        <label for="ml">Volume em mililitros/ml.</label>
        <input type="number" name="volume" id="volume" v-model="volume" />
        <label for="price">Preço.</label>
        <input type="number" name="price" id="price" min="0" step="0.01" v-model="price" />
      </form>
      <button @click="handleCount">Go</button>
    </div>
    <div class="result">
      <h2>R$ {{ result.toFixed(2).toString().replace('.', ',') }} por litro</h2>
    </div>
  </main>
</template>

<style scoped></style>
