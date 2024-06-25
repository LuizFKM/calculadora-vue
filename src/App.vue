<script setup>

</script>

<template>
  <div class="container rounded-4">
    <header class="p-5 mt-5 text-center">
      <h1>Calculadora com VueJs</h1>
      <p>Soma</p>
    </header>
    
    <form>
      <div class="row">
        <div class="col">
          <input class="form-control" type="number" placeholder="Digite o primeiro número">
        </div>
      </div>
      <div class="row">
        <div class="col mt-4">
          <input class="form-control" type="number" placeholder="Digite o segundo número">
        </div>
      </div>
      <div class="row">
        <div class="col mt-4 mb-4">
          <select class="form-control text-center">
            <option value="somar">Somar</option>
            <option value="subtrair">Subtrair</option>
            <option value="dividir">Dividir</option>
            <option value="multiplicar">Multiplicar</option>
          </select>
        </div>
      </div>
      
    </form>

  </div>
</template>

<style scoped>
.container {
  background-color: rgba(19, 27, 34, 0.534);
  color: antiquewhite;
}
</style>
