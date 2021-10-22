<template>
    <form class="mx-auto mt-4">
        <FormularioCampo nome='Nome' v-model='jogo.nome' :adicionar="registrou"></FormularioCampo>
        <FormularioCampo nome='Gênero' v-model='jogo.genero' :adicionar="registrou"></FormularioCampo>
        <button class="btn btn-primary m-2" type="button" @click='registrou'>Adicionar</button>
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
    methods: {
        registrou(){
            this.$emit("registrou", this.jogo)
        }
    },
    emits: ['registrou']
}
</script>

<style>

</style>
