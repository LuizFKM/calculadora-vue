<script setup>
  import { reactive } from 'vue';
  import Cabecalho from './components/Cabecalho.vue';
  import Formulario from './components/Formulario.vue';
  import Resultado from './components/Resultado.vue';


  const estado = reactive({
    filtro: 'somar',
    firstNumber: ' ',
    secondNumber: ' ',
    resultado: 0,
  })

  const primeiroNumero = (evento) => {
  estado.firstNumber = evento.target.value;
  getFiltroAritmetica();
};

const segundoNumero = (evento) => {
  estado.secondNumber = evento.target.value;
  getFiltroAritmetica();
};

const somaDosNumeros = () => {
  let numberOne = parseInt(estado.firstNumber)
  let numberTwo = parseInt(estado.secondNumber)
  let result = numberOne + numberTwo
  estado.resultado = result;
  return result

}

const subtracaoDosNumeros = () => {
  let numberOne = parseInt(estado.firstNumber)
  let numberTwo = parseInt(estado.secondNumber)
  let result = numberOne - numberTwo
  estado.resultado = result;
  return result
}

const divisaoDosNumeros = () => {
  let numberOne = parseInt(estado.firstNumber)
  let numberTwo = parseInt(estado.secondNumber)
  let result = numberOne / numberTwo
  estado.resultado = result;
  return result
}

const multiplicacaoDosNumeros = () => {
  let numberOne = parseInt(estado.firstNumber)
  let numberTwo = parseInt(estado.secondNumber)
  let result = numberOne * numberTwo
  estado.resultado = result;
  return result
}


const getFiltroAritmetica = () => {
  const {filtro} = estado;

  switch (filtro){
    case 'somar':
      return somaDosNumeros();
    case 'subtrair':
      return subtracaoDosNumeros();
    case 'dividir':
      return divisaoDosNumeros();
    case 'multiplicar':
      return multiplicacaoDosNumeros();
    default:
      return null
  }
  
}

const resultNan = () => {
  const {resultado} = estado
  if(isNaN(resultado)){
    return estado.resultado = 'Digite outro número'
  }
}

</script>

<template>
  <div class="container rounded-4">
    <Cabecalho :filtros-aritmetica="estado.filtro"/>
    <Formulario :primeiro-numero="primeiroNumero" :segundo-numero="segundoNumero" :estado-filtro="evento => {estado.filtro = evento.target.value; getFiltroAritmetica()}" />
    <Resultado :filtro="getFiltroAritmetica" :resultado="estado.resultado" :resultado-nan="resultNan()"/>
  </div>
</template>

<style scoped>
.container {
  background-color: rgb(19, 27, 34);
  color: antiquewhite;
}
</style>
