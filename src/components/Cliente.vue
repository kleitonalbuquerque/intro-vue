<template>
  <div id="cliente">
    <h2 class="cliente-nome">{{ nome }}</h2>
    <h3>
      <span style="color: red">Descrição do cliente:</span> {{ descricao }}
    </h3>
  </div>
</template>

<script>
export default {
  data() {
    return {
      nome: "Mariana Oliveira de Albuquerque",
      telefone: "",
      email: "",
      idade: 0,
      descricao: "Lorem ipsum lorem ipsum",
    };
  },
};
</script>

<style scoped>
#cliente {
  color: rgb(0, 255, 0);
  background-color: black;
  max-width: 600px;
  height: 150px;
  margin: 20px;
  padding: 10px;
}

.cliente-nome {
  color: rgb(255, 255, 255);
}
</style>
