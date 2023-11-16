<script setup>
    const props = defineProps(['tarefasFiltradas'])
</script>

<template>
    <header class="p-5 mb-4 mt-4 bg-light rounded-3">
        <h1>Calculadora Aritmética</h1>
        <p>
            Valor calculado: {{ props.tarefasFiltradas }}
        </p>
    </header>
</template>