<template>
  <div id="cliente">
    <h4>Nome: {{ cliente.nome }}</h4>
    <hr />
    <p>{{ descricao }}</p>
    <hr />
    <p>Telefone: {{ cliente.telefone }}</p>
    <p>E-mail: {{ cliente.email }}</p>
    <p>Idade: {{ cliente.idade }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      descricao: "Lorem ipsum lorem ipsum",
      telefone: "99999999",
    };
  },
  props: {
    nome: String,
    email: String,
    idade: Number,
    cliente: Object,
  },
};
</script>

<style scoped>
input {
  width: 400px;
}

#cliente {
  background-color: #ece5e3;
  max-width: 600px;
  height: 250px;
  padding: 1%;
  margin-top: 4px;
}
</style>
