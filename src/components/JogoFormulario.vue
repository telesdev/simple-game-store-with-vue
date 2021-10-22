<template>
    <form class="mx-auto mt-4">
        <FormularioCampo nome='Nome' v-model='jogo.nome'></FormularioCampo>
        <FormularioCampo nome='Gênero' v-model='jogo.genero'></FormularioCampo>
        <button class="btn btn-primary m-2" type="button" @click='this.$emit("registrou", this.jogo)'>Adicionar</button>
    </form>    
</template>

<script>
import FormularioCampo from "./FormularioCampo.vue";
export default {
    name : 'JogoFormulario',
    components: { FormularioCampo },
    props: {
        jogo: Object
    },
    emits: ['registrou']
}
</script>

<style>

</style>
