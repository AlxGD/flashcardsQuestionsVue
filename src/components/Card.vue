<script>
export default {
  data() {
    return {
      mostrarConteudo: false,
    };
  },
  props: {
    frente: String,
    verso: String,
  },
  methods: {
    verResposta() {
      this.mostrarConteudo = !this.mostrarConteudo;
    },
  },
};
</script>

<template>
  <div class="card" @click="verResposta">
    <div class="frente">{{ frente }}</div>
    <div class="verso" v-show="mostrarConteudo">{{ verso }}</div>
  </div>
</template>

<style scoped>
.card {
  width: 200px;
  height: 150px;
  background-color: rgba(242, 242, 242, 0.41);
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
}

.frente {
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 10px;
}

.verso {
  font-size: 20px;
  color: #555;
  display: none;
}

body {
  font-family: Helvetica, Arial, sans-serif;
}

</style>
