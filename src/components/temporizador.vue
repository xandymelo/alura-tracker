<template>
    <div class="column is-2 is-justify-content-space-between is-align-items-center is-flex">
        <Cronometro :tempo-em-segundos="tempoEmSegundos"></Cronometro>
        <Botao v-on:ao-clicar-no-botao="iniciar" titulo="play" classe-botao="fa-play" :desabilitado="cronometroRodando"></Botao>
        <Botao titulo="stop" v-on:ao-clicar-no-botao="parar" classe-botao="fa-stop" :desabilitado="!cronometroRodando"></Botao>
    </div>
</template>

<script lang="ts">
    import { defineComponent } from 'vue'
    import Cronometro from './cronometro.vue'
import Botao from './botao.vue';

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
        components: { Cronometro, Botao }
    })
</script>

<style>
</style>
