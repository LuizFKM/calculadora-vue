<script setup>
import { defineProps } from 'vue';

const props = defineProps(['primeiroNumero', 'segundoNumero', 'estadoFiltro', 'filtroEscolhido']);

const handlePrimeiroNumero = (evento) => {
    try {
        props.primeiroNumero(evento);
    } catch (error) {
        console.error("Erro ao manipular o primeiro número:", error);
    }
};

const handleSegundoNumero = (evento) => {
    try {
        props.segundoNumero(evento);
    } catch (error) {
        console.error("Erro ao manipular o segundo número:", error);
    }
};

const handleEstadoFiltro = (evento) => {
    try {
        props.estadoFiltro(evento);
    } catch (error) {
        console.error("Erro ao manipular o estado do filtro:", error);
    }
};
</script>

<template>
    <div class="d-flex justify-content-center">
        <form>
            <div class="row">
                <div class="col">
                    <input @input="handlePrimeiroNumero" class="form-control" type="number"
                        placeholder="Primeiro número">
                </div>
            </div>
            <div class="row">
                <div class="col mt-4">
                    <input @input="handleSegundoNumero" class="form-control" type="number" placeholder="Segundo número">
                </div>
            </div>
            <div class="row">
                <div class="col mt-4 mb-5">
                    <select @change="handleEstadoFiltro" class="form-control text-center">
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
