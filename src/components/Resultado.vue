<script setup>
const props = defineProps(['filtro', 'resultado', 'resultadoNan']);
</script>

<template>
    <div class="row p-5">
        <div class="col text-center">
            <h3>Resultado</h3>
            <h5 v-if="typeof props.resultado === 'number'" class="p-4">{{ props.resultado }}</h5>
            <h5 v-else-if="props.resultadoNan" class="p-4">{{ props.resultado }}</h5>
            
        </div>
    </div>
</template>
