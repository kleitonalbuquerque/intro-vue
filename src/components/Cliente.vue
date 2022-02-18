<template>
  <div :class="{ cliente: !isPremium, 'cliente-premium': isPremium }">
    <h4>Nome: {{ cliente.nome | stringUpperCase }}</h4>
    <hr />
    <p>Descriçao: {{ descricao }}</p>
    <hr />
    <p>Telefone: {{ telefone }}</p>
    <p>E-mail: {{ cliente.email | stringUpperCase }}</p>
    <p v-if="showIdade === true">Idade: {{ cliente.idade }}</p>
    <p v-else style="color: red">Idade escondida!</p>
    <!-- <p>{{ isPremium }}</p> -->
    <p>{{ categoria }}</p>
    <button @click="mudarCor($event)">Mudar categoria</button>
    <button @click="emitirEventoDelete">Deletar</button>
    <h4>ID Especial: {{ idEspecial }}</h4>
  </div>
</template>

<script>
export default {
  data() {
    return {
      descricao: "Lorem ipsum lorem ipsum",
      telefone: "99999999",
      isPremium: false,
      categoria: "STANDARD",
    };
  },
  props: {
    cliente: Object,
    showIdade: Boolean,
  },
  methods: {
    mudarCor: function ($event) {
      console.log($event);
      // troca a classe
      this.isPremium = !this.isPremium;

      // Informa se o cliente é Standard ou Premium
      if (this.isPremium === false) {
        this.categoria = "STANDARD";
      } else {
        this.categoria = "PREMIUM";
      }
    },
    emitirEventoDelete: function () {
      console.log("Emitindo evento do filho!");
      this.$emit("meDelete", {
        clienteId: this.cliente.id,
        curso: "Formação NodeJS",
        emPromocao: true,
        aluno: "Kleiton Albuquerque",
        component: this,
      });
    },
    testar: function () {
      console.log("Testando para valer!");
      alert("Isso é um alert!");
    },
  },
  filters: {
    stringUpperCase: function (value) {
      return value.toUpperCase();
    },
  },
  computed: {
    idEspecial: function () {
      return (
        this.cliente.email +
        this.cliente.nome +
        this.cliente.id
      ).toUpperCase();
    },
  },
};
</script>

<style scoped>
input {
  width: 400px;
}

.cliente {
  background-color: #ece5e3;
  max-width: 600px;
  height: 350px;
  padding: 1%;
  margin-top: 4px;
}

.cliente-premium {
  background-color: #000;
  color: gold;
  max-width: 600px;
  height: 300px;
  padding: 1%;
  margin-top: 4px;
}
</style>
