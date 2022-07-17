<template>
  <div id="app">
    <label> Número de Tabs: </label>
    <button @click="increment()">{{ count }}</button>
    <br />
    <br />
    <hr />
    <div v-for="(a, i) in quant" :key="i">
      <label> Titulo: </label>
      <input
        class="texto"
        v-model="ola[i]"
        @change="addTitulo(i, this.ola[i])"
      />
      <br />
      <label> Conteúdo: </label>
      <textarea
        class="textoConteudo"
        v-model="alo[i]"
        @change="addConteudo(i, this.alo[i])"
      >
      </textarea>
    </div>
    <button class="botao" @click="submeter()">Submeter</button>
  </div>
  <div class="tabs" v-if="nivel === 1">
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
.tabs {
  padding: 20px;
  margin: 10px 0;
  border-radius: 10px;
  border: 1px solid #aaa;
  background-color: #4CAF50;
  width: 100%;
  height: 300px;
}
.textoConteudo {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}
.botao {
  width: 50%;
  margin: 25%;
  background-color: #4CAF50;
  color: white;
  padding: 14px 20px;
  margin-left: 25%;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.texto {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}

.principal {
  width: 50%;
}
</style>