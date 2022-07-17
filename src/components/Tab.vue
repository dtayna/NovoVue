<template>
  <div id="Tab">
    <div class="botoes" v-for="(item, i) in topos" :key="i">
      <button @click="selecionaTab(i)">{{ item }}</button>
    </div>
    <br />
    <div class="corpo">
      <p>{{ corpos[tabS] }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    topos: [],
    corpos: [],
  },

  data() {
    return {
      count: 0,
      tabS: 0,
    };
  },
  methods: {
    increment() {
      this.count++;
    },
    selecionaTab(id) {
      this.tabS = id;
    },
  },
};
</script>

<style scoped>
.botoes {
  margin: 10px;
  width: 50px;
  float: left;
}

.corpo {
  width: 100px;
}
</style>