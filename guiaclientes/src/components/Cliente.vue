<template>
    <div :class="{'cliente': !isPremium,'cliente-premium': isPremium}">
        <h4>Nome: {{cliente.nome}}</h4>
        <hr>
        <p>{{descricao}}</p>
        <hr>
        <p>Número: {{cliente.numero}}</p>
        <p>e-mail: {{cliente.email | processarEmail}}</p>
        <p v-if="showIdade">Idade: {{cliente.idade}}</p>
        <p v-else>O usuário preferiu esconder a idade</p><!-- existe tbm a tag v-else-if, aonde eu posso colocar quantas consições eu quiser -->
        <button id="premium" @click="mudarCor">Mudar cor</button><br>
        <button id="deletar" @click="eventoDelet">Deletar</button>
        <h4>Id especial: {{idEspecial}}</h4>
    </div>
</template>

<script>
export default {
    data(){
        return {
            descricao: "Testador de software junior na Compasso UOL, futuro programador",
            isPremium: false
        }
    },
    props: {
        cliente: Object,
        showIdade: Boolean
    },
    methods: {
        mudarCor: function(){
            this.isPremium = !this.isPremium;
        },
        eventoDelet: function(){
            this.$emit("meDelete",{idDoCliente:this.cliente.id})
        }
    },
    filters: {
        processarEmail: function(value){
            return value.toUpperCase();
        }
    },
    computed: {
        idEspecial: function(){
            return (this.cliente.email + this.cliente.nome + this.cliente.id).toUpperCase();
        }
    }
}
</script>
<!-- aqui em style, caso uma propriedade comece com #, ele referencia um id de uma aplicação,
caso comece com ., ele referencia uma classe da aplicação -->
<style scoped>

    #premium{
        background-color: rgb(91, 27, 150);
        color: rgb(224, 221, 221);
    }

    #deletar{
        background-color: red;
        color: rgb(224, 221, 221);
        margin-top: 0.5%;
    }

    .cliente{
        background-color: #F0F0F0;
        max-width: 600px;
        max-height: 500px;
        padding: 2%;
        margin-top: 1%;
    }

    .cliente-premium{
        background-color: gold;
        max-width: 600px;
        max-height: 500px;
        padding: 2%;
        margin-top: 1%;
    }
</style>>
<!-- aqui com o componente style definimos o estilo do componente com o id, exemplo:
vemos que a div acima tem um id chamado "cliente", para definir o estilo deste componente
é só colocar um #{id o componente} e dentro dele colocar os estilos, muito simples -->