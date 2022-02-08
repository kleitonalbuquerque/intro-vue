<template>
  <div id="app">
    <h1>Guia Clientes</h1>
    <!-- <Cliente :cliente="clienteMariana" showIdade="true" /> -->
    <Cliente
      nome="Mariana"
      email="mariana@testemail.com"
      :idade="2"
      :showIdade="true"
    />
    <Cliente
      nome="Rafaella"
      email="rafa@testemail.com"
      :idade="18"
      :showIdade="true"
    />
    <Cliente
      nome="Luiz Paulo"
      email="lp@testemail.com"
      :idade="16"
      :showIdade="false"
    />
    <Cliente
      nome="Diana"
      email="diana@testemail.com"
      :idade="13"
      :showIdade="true"
    />
    <Cliente
      nome="Beatriz"
      email="bia@testemail.com"
      :idade="10"
      :showIdade="true"
    />
  </div>
</template>

<script>
import Cliente from "./components/Cliente.vue";

export default {
  name: "App",
  data() {
    return {
      clienteMariana: {
        nome: "Mariana",
        email: "mariana@testemail.com",
        idade: 2,
      },
    };
  },
  components: {
    Cliente,
  },
};
</script>

<style></style>
