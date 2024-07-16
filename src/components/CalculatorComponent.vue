<script setup>
import { ref } from 'vue'

const price = ref(0)
const volume = ref(0)

const handlePrice = (e) => {
  price.value = e.target.value
  console.log(price.value)
}

const handleVolume = (e) => {
  volume.value = e.target.value
  console.log(volume.value)
}
</script>

<template>
  <header>
    <h1>Beer calculatorrr</h1>
  </header>

  <main>
    <div>
      <form>
        <label for="price">Preço.</label>
        <input type="number" name="price" id="price" step="any" v-on:change="handlePrice" />
        <label for="ml">Volume em mililitros / ml.</label>
        <input type="number" name="volume" id="volume" v-on:change="handleVolume" />
      </form>
    </div>
    <div class="result">
      <h2>{{ volume / price }}</h2>
    </div>
  </main>
</template>

<style scoped></style>
