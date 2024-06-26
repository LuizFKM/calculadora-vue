<script setup>
  import { reactive } from 'vue';


  const estado = reactive({
    filtro: 'somar',
    firstNumber: ' ',
    secondNumber: ' ',
    resultado: 0,
  })

function primeiroNumero(evento){
  return estado.firstNumber = evento.target.value
  getFiltroAritmetica()
}
function segundoNumero(evento){
  return estado.secondNumber = evento.target.value
  getFiltroAritmetica()
}

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

</script>

<template>
  <div class="container rounded-4">
    <header class="p-5 mt-5 text-center">
      <h1>Calculadora com VueJs</h1>
      <h2>Você escolheu {{estado.filtro}}</h2>
    </header>
    <div class="d-flex justify-content-center">
      
      <form >
        <div class="row">
          <div class="col">
            <input @keyup="primeiroNumero" class="form-control" type="number" placeholder="Primeiro número">
          </div>
        </div>
        <div class="row">
          <div class="col mt-4">
            <input @keyup="segundoNumero" class="form-control" type="number" placeholder="Segundo número">
          </div>
        </div>
        <div class="row">
          <div class="col mt-4 mb-5">
            <select @change="evento => {estado.filtro = evento.target.value; getFiltroAritmetica()}" class="form-control text-center">
              <option value="somar">Somar</option>
              <option value="subtrair">Subtrair</option>
              <option value="dividir">Dividir</option>
              <option value="multiplicar">Multiplicar</option>
            </select>
          </div>
        </div>
      </form>
    </div>

    <div class="row p-5">
      <div class="col text-center">
        <h3>Resultado</h3>
        <h5  v-if="getFiltroAritmetica()"  class="p-4">{{ estado.resultado }}</h5>
        <h5  v-else class="p-4">0</h5>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  background-color: rgb(19, 27, 34);
  color: antiquewhite;
}
</style>
