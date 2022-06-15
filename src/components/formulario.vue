<template>
    <div class="box">
        <div class="columns">
            <div class="column is-8" role="form" aria-label="Formulario para criação de uma novo objeto">
                <input type="text" class="input" placeholder="Qual tarefa você deseja iniciar ?" v-model="tarefa">
            </div>
            <Temporizador @aoPararCronometro="finalizarContador" />
        </div>

    </div>
</template>

<script lang="ts">
    import { stringifyStyle } from '@vue/shared';
import { defineComponent } from 'vue'
    import Temporizador from './temporizador.vue'
    export default defineComponent({
    name: "MyFormulario",
    data() {
        return {
            tarefa: '',
        };
    },
    methods: {
        finalizarContador(tempo: number): void {
            console.log('tempo decorrido :', tempo)
            console.log('tarefa:', this.tarefa)
            this.tarefa = ''
        }
    },
    components: { Temporizador }
})
</script>

<style>
</style>
