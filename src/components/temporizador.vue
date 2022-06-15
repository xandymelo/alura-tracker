<template>
    <div class="column is-2 is-justify-content-space-between is-align-items-center is-flex">
        <Cronometro :tempo-em-segundos="tempoEmSegundos"></Cronometro>
        <button class="button" @click="iniciar" :disabled="cronometroRodando">
            <span class="icon">
                <i class="fas fa-play"></i>
            </span>
            <span>play</span>
        </button>
        <button class="button" @click="parar" :disabled="!cronometroRodando">
            <span class="icon">
                <i class="fas fa-stop"></i>
            </span>
            <span>stop</span>
        </button>
    </div>
</template>

<script lang="ts">
    import { defineComponent } from 'vue'
    import Cronometro from './cronometro.vue'

    export default defineComponent({
        name: 'MyTemporizador',
        data() {
        return {
            tempoEmSegundos: 0,
            cronometro: 0,
            cronometroRodando: false,
        };
        },
        emits: ['aoPararCronometro'],
        methods: {
            iniciar() {
                this.cronometroRodando = true
                this.cronometro = setInterval(() => {
                    this.tempoEmSegundos += 1;
                }, 1000);
            },
            parar() {
                this.cronometroRodando = false
                clearInterval(this.cronometro);
                this.$emit('aoPararCronometro', this.tempoEmSegundos)
                this.tempoEmSegundos = 0
            }
        },
        components: { Cronometro }
    })
</script>

<style>
</style>
