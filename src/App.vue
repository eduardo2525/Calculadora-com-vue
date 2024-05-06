<script setup>
  import { reactive } from 'vue';
  import Cabecalho from './components/Cabecalho.vue';
  import Operacao from './components/Operacao.vue'
  import Resultado from './components/Resultado.vue'

  const estado = reactive({
    operation: 'adicao',
    firtsNumber: '',
    secondNumber: ''
  })

  const resultado = () => {
    const {operation} = estado

    switch(operation) {
      case 'subtracao':
        return parseFloat(estado.firtsNumber) - parseFloat(estado.secondNumber)
      case 'multiplicacao':
        return parseFloat(estado.firtsNumber) * parseFloat(estado.secondNumber)
      case 'divisao':
        return parseFloat(estado.firtsNumber) / parseFloat(estado.secondNumber)
      default:
        return parseFloat(estado.firtsNumber) + parseFloat(estado.secondNumber)
    }
  }
</script>

<template>
  <div class="container">
    <Cabecalho></Cabecalho>
    <form>
      <Operacao :operacao="evento => estado.operation = evento.target.value" :firtsNumber="evento => estado.firtsNumber = evento.target.value" :secondNumber="evento => estado.secondNumber = evento.target.value"></Operacao>
      <Resultado :firtsNumber="estado.firtsNumber" :secondNumber="estado.secondNumber" :resultado="resultado()"></Resultado>
    </form>
  </div>
</template>

<style scoped>
* {
  margin: 0;
  padding: 0;
}

.container {
  max-width: 1366px;
  max-height: 500px;
  margin: 0 auto;
}

form {
  width: 70%;
  height: 300px;
  margin: 0 auto;
  background-color: rgb(213, 243, 239);
  border-radius: 30px;
}
</style>
