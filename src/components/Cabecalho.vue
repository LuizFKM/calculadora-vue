<script setup>
const props = defineProps(['filtrosAritmetica'])
</script>

<template>
    <header class="p-5 mt-5 text-center">
        <h1>Calculadora com VueJs</h1>
        <h2>Você escolheu {{props.filtrosAritmetica}}</h2>
    </header>
</template>