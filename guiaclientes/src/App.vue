<template>
  <div id="app">
    <div v-for="cliente in clients" :key="cliente.numero">
      <Cliente :cliente="cliente"/>
    </div>
  </div>
</template>

<script>

import Cliente from "./components/Cliente.vue";

export default {
  name: 'App',
  data(){
    return {
    clients: [
      {
        nome: "Pedro Henrique Ruas Maschio",
        numero: "54887",
        email: "pedro.maschio@compasso.com.br",
        idade: "20",
      },
      {
        nome: "Larissa Rodrigues Rech",
        numero: "87435",
        email: "laryyy@gmail.com",
        idade: "19"
      },
      {
        nome: "Tobias Bobco Marcolan",
        numero: "16408",
        email: "tobias2011@yahoo.com",
        idade: "22"
      },
      {
        nome: "Henrique Candeia Biolchi",
        numero: "15086",
        email: "henrique.biolchi@hotmail.com",
        idade: "21"
      }
    ]
    }
  },
  components: {
    Cliente
  }
}
</script>

<style>

</style>
