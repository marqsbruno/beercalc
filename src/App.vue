<script setup>
import CalculatorComponent from './components/CalculatorComponent.vue'
</script>

<template>
  <main>
    <CalculatorComponent />
  </main>
</template>

<style scoped>
main {
  margin: 20px;
  border: 1px solid black;
  border-radius: 10px;
  padding: 15px;
  background-color: white;

  display: flex;
  flex-direction: column;
  align-items: center;
  align-self: center;
  width: max-content;
}
</style>
