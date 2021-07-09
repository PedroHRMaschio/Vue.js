<template>
    <div id="cliente">
        <h2 id="cliente-nome">{{ nome }}</h2> <!-- Usando o simblolo {{}} é possível exibir variáveis e chamar funções -->
        <p>Descrição: {{ descricao }}</p>
    </div>
</template>

<script>
export default {
    data(){
        return {
            nome : "Pedro Henrique",
            numero: "(54) 99682-2112",
            email: "pedro.maschio@compasso.com.br",
            idade: 20,
            descricao: "Testador de software junior na Compasso UOL, futuro programador"
        }
    }
    
}
</script>

<!-- aqui con componente style definimos o estilo do componente com o id, exemplo:
vemos que a div acima tem um id chamado "cliente", para definir o estilo deste componente
é só colocar um #{id o componente} e dentro dele colocar os estilos, muito simples -->


<style scoped>
    #cliente{
        color: greenyellow;
        background-color: gray;
    }

    #cliente-nome{
        color: white;
    }
</style>>
