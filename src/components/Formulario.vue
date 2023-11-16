<script setup>
    const props = defineProps(['primeiroNumero', 'segundoNumero', 'trocarFiltro'])
</script>

<template>
    <form>
        <div class="row">
            <div class="col" >
                <input @keyup="props.primeiroNumero" type="number" placeholder="Digite um número" class="form-control">
                <input @keyup="props.segundoNumero" type="number" placeholder="Digite um número" class="form-control">
            </div>
            <div class="col-md-2">
                <select @change="props.trocarFiltro" class="form-control">
                <option value="somar">Somar</option>
                <option value="subtrair">Subtrair</option>
                <option value="multiplicacao">Multiplicar</option>
                <option value="dividir">Dividir</option>
                </select>
            </div>
            <div class="col-md-2">
                <button type="submit" class="btn btn-primary">Finalizar</button>
            </div>
        </div>
    </form>
    
</template>

<style scoped>
    .form-control {
        margin-bottom: 6px;
    }
</style>