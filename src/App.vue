<template>
  <div id="app">
    <h1>Guia Clientes</h1>
    <div v-for="cliente in clientes" :key="cliente.id">
      <p>
        <Cliente :cliente="cliente" :showIdade="true" />
      </p>
      <label for="">Editar: </label>
      <input type="text" v-model="cliente.nome" />
      <input type="text" v-model="cliente.email" />
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
};
</script>

<style></style>
