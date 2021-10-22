<template>
    <div class="card mx-auto my-3 rounded-3 shadow-sm" style="width: 18rem;">
        <div class='card-body'>
            <h5 class="card-title">{{ jogo.nome }}</h5>
            <p class="card-text">{{ jogo.genero }}</p>
        </div>
        <button class="btn btn-outline-success mx-3 mb-4">Alugar</button>
        <button class="btn btn-outline-secondary mx-3 mb-4">Editar</button>
        <button class="btn btn-outline-danger mx-3 mb-4" @click='apagar(jogo)'>Deletar</button>
    </div>
</template>

<script>
export default {
    name : 'JogoItem',
    props: {
        jogos: Array,
        jogo: Object
    },
    methods: {
        apagar(jogo) {
            this.jogos.splice(this.jogos.indexOf(jogo), 1)
        }
    }

}
</script>

<style>

</style>
