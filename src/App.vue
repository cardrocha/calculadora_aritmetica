<script setup>

import { reactive } from 'vue';

const estado = reactive ({
  operacao: '',
  numb1: 0,
  numb2: 0,
  // value: '',
})

const operacaoSoma = () => {
  return parseInt(estado.numb1) + parseInt(estado.numb2);
}

const operacaoSubtracao = () => {
  return estado.numb1 - estado.numb2;
}

const operacaoMultiplicacao = () => {
  return estado.numb1 * estado.numb2;
}

const operacaoDivisao = () => {
  return estado.numb1 / estado.numb2;
}

// const getOperacaoSelecionada = () => {
//   const {operacao} = estado;

//   switch (operacao) {
//     case 'adicao':
//       return  operacaoSoma();
//     case 'subtracao':
//       return operacaoSubtracao();
//     case 'multiplicacao':
//       return operacaoMultiplicacao();
//     case 'divisao':
//       return operacaoDivisao();
//   }
//   return resultado;
// }

// function campoSelect(result) {
//   let select = document.querySelector('#opcao');
//   let optionValue = select.options[select.selectedIndex];
  
//   let value = optionValue.value;
//   let resultado = optionValue.text;
  
// }

</script>

<template>
  <header class="p-5 mb-4 mt-4 bg-dark rounded-3">
    <div class="container">
      <h1>Calculadora Aritmética</h1>
      <!-- <span class="p-2 mb-2 mt-2 bg-light rounded-3 col-md-1">{{  }}</span> -->
    </div>
  </header>
  <form>
    <div class="row">
      <div class="col-md-2 me-1 ms-5 ">
        <input type="number" @change="evento => estado.numb1 = evento.target.value" placeholder="insira um número" class="form-control">
      </div>
      <div class="col-md-2">
        <input type="number" @change="evento => estado.numb2 = evento.target.value" placeholder="insira um número" class="form-control">
      </div>
      <div class="col-md-3">
        <select id="opcao" class="form-control text-center">
          <option selected disabled value="">Escolha a operação</option>
          <option>(+) Adição = {{ operacaoSoma() }}</option>
          <option>(-) Subtração = {{ operacaoSubtracao() }}</option>
          <option>(*) Multiplicação = {{ operacaoMultiplicacao() }}</option>
          <option>(÷) Divisão = {{ operacaoDivisao() }}</option>
        </select>
      </div>
    </div>
  </form>
</template>

<style scoped>
.container {
  color: #fff;
}
</style>