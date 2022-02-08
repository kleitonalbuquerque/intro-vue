<template>
  <div id="cliente">
    <h4>Nome: {{ nome }}</h4>
    <hr />
    <p>{{ descricao }}</p>
    <hr />
    <p>Telefone: {{ telefone }}</p>
    <p>E-mail: {{ email }}</p>
    <p v-if="showIdade === true">Idade: {{ idade }}</p>
    <p v-else style="color: red">Idade escondida!</p>
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
    showIdade: Boolean,
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
