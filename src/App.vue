<script setup>
import { reactive } from 'vue';
import Formulario from './components/Formualrio.vue'

const estado = reactive({
  acao: 'adicao',
  valor1: 0,
  valor2: 0
})

const operacao = () => {
  let { acao, valor1, valor2 } = estado

  switch (acao) {
    case 'adicao':
      return valor1 + valor2
    case 'subtracao':
      return valor1 - valor2
    case 'multiplicacao':
      return valor1 * valor2
    case 'divisao':
      if (valor2 == 0) {
        return 'Não é possível'
      } else {
        return valor1 / valor2
      }
  }
}
</script>

<template>
  <div class="container">
    <h1 class="text-center mt-5">Calculadora Aritmética</h1>
      <Formulario :primeiro-valor="e => estado.valor1 = e.target.value" :segundo-valor="e => estado.valor2 = e.target.value" :muda-acao="e => estado.acao= e.target.value" :operacao="operacao()"/>
  </div>
</template>

<style scoped></style>
