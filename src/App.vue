<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Formulario from './components/Formulario.vue';

  const estado = reactive({
    filtro: 'somar',
    n1: 0,
    n2: 0
  })


  function getSomar() {
    const {n1, n2} = estado;
    return parseInt(n1) + parseInt(n2);
  }

  function getSubtrair() {
    const {n1, n2} = estado;
    return parseInt(n1) - parseInt(n2);
  }

  function getMultiplicar() {
    const {n1, n2} = estado;
    return parseInt(n1) * parseInt(n2);
  }

  function getDividir() {
    const {n1, n2} = estado;
    return parseInt(n1) / parseInt(n2);
  }

  const getTarefasFiltradas = () => {
    const { filtro } = estado;

    switch(filtro) {
      case 'somar':
        return getSomar();
      case 'subtrair':
        return getSubtrair();
      case 'multiplicacao':
        return getMultiplicar();
      case 'dividir':
        return getDividir();
    }
  }

</script>

<template>
  <div class="container">    
    <Cabecalho :tarefas-filtradas="getTarefasFiltradas()" />
    <Formulario :primeiro-numero="evento => estado.n1 = evento.target.value" :segundo-numero="evento => estado.n2 = evento.target.value" :trocar-filtro="evento => estado.filtro = evento.target.value" />
  </div>
</template>


