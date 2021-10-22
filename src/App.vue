<template>
    <div class="container text-center">

        <h1>Locadora</h1>

        <hr/>

        <JogoFormulario :jogo='jogo' @registrou='cadastrar'></JogoFormulario>

        <hr/>
        
        <JogoLista>
            <JogoItem v-for="jogo in jogos" :key="jogo.id" :jogo='jogo' :jogos='jogos'></JogoItem>
        </JogoLista>

    </div>
</template>

<script>
import JogoFormulario from "./components/JogoFormulario.vue";
import JogoLista from "./components/JogoLista.vue";
import JogoItem from "./components/JogoItem.vue";

export default {
    components: {
        JogoFormulario,
        JogoLista,
        JogoItem
    },
    data () {
        return {
            jogos: [],
            jogo: {
                nome: '',
                genero: ''
            }
        }
    },
    methods: {
        carregar () {
            fetch('./src/data/jogos.json')
            .then(res => res.json())
            .then(data => this.jogos = data)
            this.jogos = []
        },
        cadastrar() {
            // if(!this.jogo.nome || !this.jogo.genero)
            //     return
            // let jogo = {
            //     id: this.jogos[this.jogos.length-1].id + 1,
            //     nome: this.jogo.nome,
            //     genero: this.jogo.genero,
            //     alugado: false
            // }
            this.jogos.push(this.jogo)
            this.jogo = {}
        }
    },
    mounted() {
        this.carregar()
    }
}
</script>

<style>

</style>
