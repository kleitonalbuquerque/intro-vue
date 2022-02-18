<template>
  <div id="app" class="container">
    <h1>Guia Clientes</h1>
    <hr />
    <h3>Cadastro:</h3>
    <small class="error" v-show="deuErro">O nome não pode ser vazio!</small
    ><br />
    <input type="text" id="nome" placeholder="nome" v-model="nomeField" /><br />
    <small class="error" v-show="deuErro">O e-mail não pode ser vazio!</small
    ><br />
    <input
      type="email"
      id="email"
      placeholder="e-mail"
      v-model="emailField"
    /><br />
    <small class="error" v-show="deuErro"
      >A idade deve ser igual ou maior que zero!</small
    ><br />
    <input
      type="number"
      id="idade"
      placeholder="idade"
      v-model="idadeField"
    /><br /><br />
    <div class="buttons">
      <button class="button is-primary" @click="cadastrarUsuario">
        Cadastrar
      </button>
    </div>
    <hr />
    <div v-for="cliente in orderClientes" :key="cliente.id">
      <p>
        <Cliente
          :cliente="cliente"
          :showIdade="true"
          @meDelete="deletarUsuario($event)"
        />
      </p>
      <hr />
    </div>
  </div>
</template>

<script>
import _ from "lodash";
import Cliente from "./components/Cliente.vue";

export default {
  name: "App",
  data() {
    return {
      deuErro: false,
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
      if (this.nomeField === "") {
        alert("Por favor informe o nome!");
        document.getElementById("nome").focus();
        this.deuErro = true;
      } else if (this.emailField === "") {
        alert("Por favor informe o e-mail!");
        document.getElementById("email").focus();
        this.deuErro = true;
      } else if (this.idadeField < 0) {
        alert("Por favor informe a idade!");
        document.getElementById("idade").focus;
        this.deuErro = true;
      } else {
        this.clientes.push({
          nome: this.nomeField,
          email: this.emailField,
          idade: this.idadeField,
          id: Date.now(),
        });
        this.deuErro = false;
      }
      (this.nomeField = ""), (this.emailField = ""), (this.idadeField = 0);
    },
    deletarUsuario: function ($event) {
      console.log("Recebendo evento!");
      // console.log($event.clienteId);
      // $event.component.testar();
      var id = $event.clienteId;
      var novoArray = this.clientes.filter((cliente) => cliente.id != id);
      this.clientes = novoArray;
    },
  },
  computed: {
    orderClientes: function () {
      return _.orderBy(this.clientes, ["nome"], ["asc"]);
    },
  },
};
</script>

<style>
.error {
  color: red;
}
</style>
