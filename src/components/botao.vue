<template>
    <button class="button" @click="$emit('aoClicarNoBotao')" :disabled="$props.desabilitado">
        <span class="icon">
            <i class="fas" v-bind:class="$props.classeBotao"></i>
        </span>
        <span>{{titulo}}</span>
    </button>
</template>

<script lang="ts">
    import { defineComponent } from 'vue'

    export default defineComponent({
        name: 'MyBotao',
        emits: ['aoClicarNoBotao'],
        props: {
                aoClicar: {
                    type: Function,
                },
                titulo: {
                    type: String,
                    default: ''
                },
                classeBotao: {
                    type: String,
                    default: ''
                },
                desabilitado: {
                    type: Boolean,
                    default: false
                }
            },
    })
</script>

<style>
</style>
