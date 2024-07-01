<script setup>
import { ref } from 'vue';

const numero1 = ref(0);
const numero2 = ref(0);
const operacao = ref('+');

const calcularResultado = () => {
  switch (operacao.value) {
    case '+':
      return Number(numero1.value) + Number(numero2.value);
    case '-':
      return Number(numero1.value) - Number(numero2.value);
    case '*':
      return Number(numero1.value) * Number(numero2.value);
    case '/':
      return Number(numero1.value) / Number(numero2.value);
    default:
      return 0;
  }
};

</script>

<template>
  <div class="calculadora">
    <h1>Calculadora Aritmética</h1>

    <div class="form-group">
      <label for="numero1">Número 1:</label>
      <input v-model="numero1" type="number" id="numero1">
    </div>

    <div class="form-group">
      <label for="numero2">Número 2:</label>
      <input v-model="numero2" type="number" id="numero2">
    </div>

    <div class="form-group">
      <label for="operacao">Operação:</label>
      <select v-model="operacao" id="operacao">
        <option value="+">Soma (+)</option>
        <option value="-">Subtração (-)</option>
        <option value="*">Multiplicação (*)</option>
        <option value="/">Divisão (/)</option>
      </select>
    </div>

    <div class="resultado">
      <p>Resultado: {{ calcularResultado() }}</p>
    </div>
  </div>

</template>

<style scoped>
.calculadora {
  max-width: 400px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 8px;
  background-color: #f9f9f9;
  color: #000;
}

.form-group {
  margin-bottom: 15px;
}

.resultado {
  margin-top: 20px;
  font-weight: bold;
}
</style>