<script setup>
import { reactive } from 'vue';
import InputNumeros from './components/InputNumeros.vue'
import Equacoes from './components/Equacoes.vue'

const estado = reactive({
  equacao: 'soma',
  numero1: '',
  numero2: '',
})

const getPrimeiroNumero = () => {
  return parseFloat(estado.numero1) || 0
}
const getSegundoNumero = () => {
  return parseFloat(estado.numero2) || 0
}

const resltEquacao = () => {
  const num1 = getPrimeiroNumero()
  const num2 = getSegundoNumero()


  const { equacao } = estado;
  switch (equacao) {
    case 'soma':
      return num1 + num2;
    case 'subtracao':
      return num1 - num2;
    case 'divisao':
      return num1 / num2;
    case 'multiplicacao':
      return num1 * num2;
    default:
  }
}
</script>

<template>
  <div class="container bg-light rounded-3 mt-4">
    <header class="p-2 mb-4 text-center">
      <h1>CALCULADORA</h1>
    </header>
    <InputNumeros :primeiro-numero="evento => estado.numero1 = evento.target.value " :segundo-numero="evento => estado.numero2 = evento.target.value "/>
    <Equacoes :tipo-equacao="evento => estado.equacao = evento.target.value"/>
    <p class="text-center p-4">O resultado da equação é <span class="text-danger">{{ resltEquacao() }}</span></p>
  </div>
</template>

<style scoped>
.container {
  margin: auto;
  max-width: 400px;
}
</style>
