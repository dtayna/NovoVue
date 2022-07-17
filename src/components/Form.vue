<template>
  <div id="app">
    <label> Número de Tabs: </label>
    <button @click="increment()">{{ count }}</button>
    <br />
    <br />
    <div v-for="(a, i) in quant" :key="i">
      <label> Titulo: </label>
      <input v-model="ola[i]" @change="addTitulo(i, this.ola[i])" />
      <br />
      <label> Conteúdo: </label>
      <textarea v-model="alo[i]" @change="addConteudo(i, this.alo[i])">
      </textarea>
    </div>
    <button @click="submeter()">Submeter</button>
  </div>
  <div v-if="nivel === 1">
    <Tab :topos="coisa1" :corpos="coisa2" />
  </div>
</template>

<script>
import Tab from "./Tab.vue";

export default {
  components: {
    Tab: Tab,
  },
  data() {
    return {
      ola: [],
      alo: [],
      count: 0,
      quant: [],
      coisa1: [],
      coisa2: [],
      nivel: 0,
      teste: 0,
      titulos: ["a"],
      conteudos: [],
    };
  },
  methods: {
    increment() {
      this.quant[this.count] = this.count;
      this.count++;
    },
    addTitulo(j, comp) {
      this.titulos[j] = comp;
    },
    addConteudo(j, comp) {
      this.conteudos[j] = comp;
    },

    submeter() {
      this.nivel = 1;
      this.coisa1 = this.titulos;
      this.coisa2 = this.conteudos;
    },
  },
};
</script>

<style scoped>
</style>