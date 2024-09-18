<script setup>
  import Formulario from './components/Formulario.vue';
  import Clima from './components/Clima.vue';
  import Spiner from './components/Spiner.vue';
  import useClima from './composable/useClima';

  const { obtenerClima, clima, cargando, mostrarClima } = useClima()

  

</script>

<template>
  <h1 class="titulo">Buscador de clima</h1>
  <div class="contenedor buscador-clima">

    <Formulario
      @obtener-clima = "obtenerClima"
    />

    <Spiner
      v-if="cargando"
    />

    <Clima
      v-if="mostrarClima"
      :clima="clima"
    />

  </div>
</template>

