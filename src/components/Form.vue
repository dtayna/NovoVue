<template>
  <div id="app">
    <label> Número de Tabs: </label>
    <button @click="increment()">{{ count }}</button>
    <br />
    <br />
    <div v-for="(a, i) in quant" :key="i">
      <label> Titulo: </label>
      <input @change="addTitulo(i)" />
      <br />
      <label> Conteúdo: </label>
      <textarea @change="addConteudo(i, this.value)"> </textarea>
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
    addConteudo(j, comp) {
      this.conteudos[j] = comp.value;
    },
    addTitulo(j, comp) {
      this.teste = 1;
      this.titulos[j] = "ai" + comp;
    },
    submeter() {
      this.nivel = 1;
      this.coisa1 = this.titulo;
      this.coisa2 = this.conteudos;
    },
  },
};
</script>

<style scoped>
</style>