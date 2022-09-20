<script>
import axios from "axios";
export default {
  data() {
    return {
      cep: "",
      resultado: {},
    };
  },
  methods: {
    async buscar() {
      const url = "viacep.com.br/ws/${this.cep}/json/;";
      this.resultado = await axios.get(url);
    },
  },
};
</script>

<template>
  <h1>Buscar Cep</h1>
  <form @submit.prevent="buscar">
    <input type="text" v-model="cep" placeholder="Digite CEP" />
    <button type="submit">Buscar</button>
  </form>
</template>
