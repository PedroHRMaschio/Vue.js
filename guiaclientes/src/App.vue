<template>
  <div id="app">
    <h3>Cadastro: </h3>
    <small id="erro" v-show="deuErro">O nome não pode ser nulo!</small><br>
    <input type="text" placeholder="nome" v-model="nomeField"><br>
    <input type="email" placeholder="email@email.com" v-model="emailField"><br>
    <input type="number" placeholder="idade" v-model="idadeField"><br>
    <input type="number" placeholder="numero" v-model="numeroField"><br>
    <button @click="cadastrarUsuario" id="cadastro">Cadastrar</button>
    <div v-for="cliente in clients" :key="cliente.id">
      <Cliente :cliente="cliente" @meDelete="deletarUser($event)"/>
    </div>
  </div>
</template>

<script>

import Cliente from "./components/Cliente.vue";

export default {
  name: 'App',
  data(){
    return {
      deuErro: false,
      nomeField: "",
      emailField: "",
      idadeField: 0,
      numeroField: 0,
    clients: [
      {
        nome: "Pedro Henrique Ruas Maschio",
        numero: "54887",
        email: "pedro.maschio@compasso.com.br",
        idade: "20",
        id:0
      },
      {
        nome: "Larissa Rodrigues Rech",
        numero: "87435",
        email: "laryyy@gmail.com",
        idade: "19",
        id:1
      },
      {
        nome: "Tobias Bobco Marcolan",
        numero: "16408",
        email: "tobias2011@yahoo.com",
        idade: "22",
        id:2
      },
      {
        nome: "Henrique Candeia Biolchi",
        numero: "15086",
        email: "henrique.biolchi@hotmail.com",
        idade: "21",
        id:3
      }
    ]
    }
  },
  components: {
    Cliente
  },
  methods: {
    cadastrarUsuario: function(){
      if(this.nomeField == null || this.nomeField == ""){
        this.deuErro = true;
      }else{
        this.clients.push({nome: this.nomeField, email: this.emailField, idade: this.idadeField, numero: this.numeroField, id: Date.now()});
        this.nomeField = "";
        this.emailField = "";
        this.idadeField = 0;
        this.numeroField = 0;
        this.deuErro = false;
      }
    },
    deletarUser: function($event){
      var id = $event.idDoCliente;
      var novoArray = this.clients.filter(cliente => cliente.id != id);
      this.clients = novoArray;
    }
  }
}
</script>

<style scope>
  #cadastro{
    margin-top: 0.5%;
    color: rgb(26, 24, 61);
    background-color: rgb(70, 211, 70);
  }
  #erro{
    color: rgb(143, 21, 21);
  }
</style>
