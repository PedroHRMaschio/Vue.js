<template>
  <div id="app">
    <Cliente :cliente="clientePedro" :showIdade="true"/>
    <Cliente :cliente="clienteLarissa" :showIdade="true"/>
    <Cliente :cliente="clienteTobias" :showIdade="false"/>
    <Cliente :cliente="clienteChico" :showIdade="false"/>
  </div>
</template>

<script>
import Cliente from "./components/Cliente.vue";

export default {
  name: 'App',
  data(){
    return {
      clientePedro: {
        nome: "Pedro Henrique Ruas Maschio",
        numero: "54887",
        email: "pedro.maschio@compasso.com.br",
        idade: "20"
      },
      clienteLarissa: {
        nome: "Larissa Rodrigues Rech",
        numero: "87435",
        email: "laryyy@gmail.com",
        idade: "19"
      },
      clienteTobias: {
        nome: "Tobias Bobco Marcolan",
        numero: "16408",
        email: "tobias2011@yahoo.com",
        idade: "22"
      },
      clienteChico: {
        nome: "Henrique Candeia Biolchi",
        numero: "15086",
        email: "henrique.biolchi@hotmail.com",
        idade: "21"
      }
    }
  },
  components: {
    Cliente
  }
}
</script>

<style>

</style>
