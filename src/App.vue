<template>
<main class="columns is-gapless is-12">
  <div class="column is-2">
    <BarraLateral />
  </div>
  <div class="column is-10">
    <MyFormulario />
  </div>
</main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from './components/barraLateral.vue';
import MyFormulario from './components/formulario.vue';

export default defineComponent({
    name: "App",
    components: { BarraLateral, MyFormulario }
});
</script>

<style>

</style>
