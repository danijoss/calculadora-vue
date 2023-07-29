<script setup>
import { reactive } from 'vue';
import Formulario from './components/Formulario.vue'


  const estado = reactive({
    operacao: 'adicao',
    numero1: 0,
    numero2: 0,
  })

  const getOperacaoAritmetica = () => {
    const { operacao } = estado;
    
    switch (operacao){
        case 'subtracao':
          return parseFloat(estado.numero1) - parseFloat(estado.numero2);
        case 'multiplicacao':
          return parseFloat(estado.numero1) * parseFloat(estado.numero2);
        case 'divisao':
          return parseFloat(estado.numero1) / parseFloat(estado.numero2);
        default:
          return parseFloat(estado.numero1) + parseFloat(estado.numero2);
    }
  }

</script>

<template>
  <div class="container">
    <header class="p-5 mb-4 mt-4 bg-light rounded-3">
      <h1>Calculadora aritmética</h1>
    </header>
    <Formulario :operacao-aritmetica="getOperacaoAritmetica()" :trocar-operacao="evento => estado.operacao = evento.target.value" :numero-um="evento => estado.numero1 = evento.target.value" :numero-dois="evento => estado.numero2 = evento.target.value" />
  </div>
</template>

<style scoped>

</style>
