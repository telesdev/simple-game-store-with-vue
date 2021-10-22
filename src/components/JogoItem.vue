<template>
    <div class="card mx-auto my-3 rounded-3 shadow-sm border-success" style="width: 18rem;" v-if="!jogo.alugado">
        <div class='card-body'>
            <input class="py-1 mt-1 mb-3 form-control" v-if="alterando == jogo" v-model="jogo.nome" placeholder="Nome">
            <h5 class="card-title" v-else>{{ jogo.nome }}</h5>
            <input class="py-1 mb-3 form-control" v-if="alterando == jogo" v-model="jogo.genero" placeholder="Gênero">
            <p class="card-text" v-else>{{ jogo.genero }}</p>
            <button class="btn btn-outline-success mx-3 mb-4 col-10" @click='alugar'>Alugar</button>
            <button class="btn btn-outline-secondary mx-3 mb-4 col-10" @click='editar(jogo)'>Editar</button>
            <button class="btn btn-outline-danger mx-3 mb-4 col-10" @click='apagar(jogo)'>Deletar</button>
        </div>
    </div>
    <div class="card mx-auto my-3 rounded-3 shadow-sm border-danger" style="width: 18rem;" v-else>
        <div class='card-body'>
            <input class="py-1 mt-1 mb-3 form-control" v-if="alterando == jogo" v-model="jogo.nome" placeholder="Nome">
            <h5 class="card-title" v-else>{{ jogo.nome }}</h5>
            <input class="py-1 mb-3 form-control" v-if="alterando == jogo" v-model="jogo.genero" placeholder="Gênero">
            <p class="card-text" v-else>{{ jogo.genero }}</p>
            <button class="btn btn-warning mx-3 mb-4 col-10" @click='alugar'>Jogo Alugado - Devolver</button>
            <button class="btn btn-outline-secondary mx-3 mb-4 col-10" @click='editar(jogo)'>Editar</button>
            <button class="btn btn-outline-danger mx-3 mb-4 col-10" @click='apagar(jogo)'>Deletar</button>
        </div>
    </div>
    
</template>

<script>
export default {
    data: () => {
        return {
            alterando: null
        }
    },
    name : 'JogoItem',
    props: {
        jogos: Array,
        jogo: Object
    },
    methods: {
        apagar(jogo) {
            this.jogos.splice(this.jogos.indexOf(jogo), 1)
        },
        alugar() {
            this.jogo.alugado = !this.jogo.alugado
        },
        editar(jogo) {
            if (this.alterando !== jogo){
                this.alterando = jogo
            } else {
                this.alterando = null
            }
        }
    }
}
</script>

<style>

</style>
