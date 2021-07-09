<template>
    <div id="cliente">
        <h4>Nome: {{cliente.nome}}</h4>
        <hr>
        <p>{{descricao}}</p>
        <hr>
        <p>Número: {{cliente.numero}}</p>
        <p>e-mail: {{cliente.email}}</p>
        <p v-if="showIdade">Idade: {{cliente.idade}}</p>
        <p v-else>O usuário preferiu esconder a idade</p><!-- existe tbm a tag v-else-if, aonde eu posso colocar quantas consições eu quiser -->
    </div>
</template>

<script>
export default {
    data(){
        return {
            descricao: "Testador de software junior na Compasso UOL, futuro programador"
        }
    },
    props: {
        cliente: Object,
        showIdade: Boolean
    }
}
</script>

<style scoped>
    #cliente{
        background-color: #F0F0F0;
        max-width: 600px;
        max-height: 500px;
        padding: 2%;
        margin-top: 1%;
    }
</style>>
<!-- aqui com o componente style definimos o estilo do componente com o id, exemplo:
vemos que a div acima tem um id chamado "cliente", para definir o estilo deste componente
é só colocar um #{id o componente} e dentro dele colocar os estilos, muito simples -->