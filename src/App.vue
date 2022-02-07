<template>
  <div id="app">
    <h1>Guia Clientes</h1>
    <Cliente :cliente="clienteMariana" />
    <Cliente nome="Rafaella" email="rafa@testemail.com" idade="18" />
    <Cliente nome="Luiz Paulo" email="lp@testemail.com" idade="16" />
    <Cliente nome="Diana" email="diana@testemail.com" idade="13" />
    <Cliente nome="Beatriz" email="bia@testemail.com" idade="10" />
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
