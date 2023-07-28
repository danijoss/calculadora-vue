<script setup>
import { reactive } from 'vue';


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
    {{ numero1 }}
    <form>
      <div class="row">
        <div class="col-3">
          <input @change="evento => estado.numero1 = evento.target.value" type="number" placeholder="Digite um número" class="form-control">
        </div>
        <div class="col-1">
          <select @change="evento => estado.operacao = evento.target.value" class="form-control">
            <option value="adicao">+</option>
            <option value="subtracao">-</option>
            <option value="multiplicacao">x</option>
            <option value="divisao">/</option>
          </select>
        </div>
        <div class="col-3">
          <input @change="evento => estado.numero2 = evento.target.value" type="number" placeholder="Digite um número" class="form-control">
        </div>
        <div class="col p-1">
          <h3>=</h3>
        </div>
        <div class="col-4 pt-1">
          <h3>{{ getOperacaoAritmetica()}}</h3>
        </div>
      </div>
    </form>
  </div>
</template>

<style scoped>

</style>
