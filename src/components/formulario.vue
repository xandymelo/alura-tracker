<template>
    <div class="box">
        <div class="columns">
            <div class="column is-8" role="form" aria-label="Formulario para criação de uma novo objeto">
                <input type="text" class="input" placeholder="Qual tarefa você deseja iniciar ?">
            </div>
            <div class="column is-2 is-justify-content-space-between is-align-items-center is-flex">
                <section>
                    <strong>
                        {{tempoDecorrido}}
                    </strong>
                </section>
                <button class="button" @click="iniciar">
                    <span class="icon">
                        <i class="fas fa-play"></i>
                    </span>
                    <span>play</span>
                </button>
                <button class="button" @click="parar">
                    <span class="icon">
                        <i class="fas fa-stop"></i>
                    </span>
                    <span>stop</span>
                </button>
            </div>
        </div>

    </div>
</template>

<script lang="ts">
    import { defineComponent } from 'vue'

    export default defineComponent({
        name: 'MyFormulario',
        data () {
            return {
                tempoEmSegundos : 0,
                cronometro : 0
            }
        },
        computed: {
            tempoDecorrido () : string {
                return new Date(this.tempoEmSegundos * 1000).toISOString().substring(11,19)
            }
        },
        methods: {
            iniciar () {
                this.cronometro = setInterval(() => {
                    this.tempoEmSegundos += 1
                }, 1000)
            },
            parar () {
                clearInterval(this.cronometro)
            }
        }
    })
</script>

<style>
</style>
