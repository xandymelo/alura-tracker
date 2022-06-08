<template>
    <header>
        <h1>
            <img src="../assets/logo.png" alt="alura-tracker">
        </h1>
    </header>
</template>

<script lang="ts">
    import { defineComponent } from 'vue'

    export default defineComponent({
        name: 'BarraLateral'
    })
</script>

<style>
    header {
    padding: 1rem;
    background: #FFD700;
    width: 100%;
    height: 100vh;
    border-bottom-right-radius: 10px;
    border-top-right-radius: 10px;
    }
    @media only screen and (max-width: 768px) {
        header {
            padding: 2.5rem;
            height: auto;
        }
    }
</style>
