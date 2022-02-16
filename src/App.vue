<template>
  <div id="app">
    <h1>Guia Clientes</h1>
    <hr />
    <h3>Cadastro:</h3>
    <input type="text" placeholder="nome" v-model="nomeField" /><br />
    <input type="email" placeholder="e-mail" v-model="emailField" /><br />
    <input type="number" placeholder="idade" v-model="idadeField" /><br />
    <button @click="cadastrarUsuario">Cadastrar</button>
    <hr />
    <div v-for="cliente in clientes" :key="cliente.id">
      <p>
        <Cliente :cliente="cliente" :showIdade="true" />
      </p>
      <hr />
    </div>
  </div>
</template>

<script>
import Cliente from "./components/Cliente.vue";

export default {
  name: "App",
  data() {
    return {
      nomeField: "",
      emailField: "",
      idadeField: 0,
      clientes: [
        {
          id: 1,
          nome: "Mariana",
          email: "mariana@testemail.com",
          idade: 2,
        },
        {
          id: 2,
          nome: "Rafa",
          email: "rafa@testemail.com",
          idade: 18,
        },
        {
          id: 3,
          nome: "Luiz",
          email: "luiz@testemail.com",
          idade: 16,
        },
        {
          id: 4,
          nome: "Diana",
          email: "diana@testemail.com",
          idade: 12,
        },
        {
          id: 5,
          nome: "Bia",
          email: "bia@testemail.com",
          idade: 10,
        },
      ],
    };
  },
  components: {
    Cliente,
  },
  methods: {
    cadastrarUsuario: function () {
      this.clientes.push({
        nome: this.nomeField,
        email: this.emailField,
        idade: this.idadeField,
        id: Date.now(),
      });
      (this.nomeField = ""), (this.emailField = ""), (this.idadeField = 0);
    },
  },
};
</script>

<style></style>
