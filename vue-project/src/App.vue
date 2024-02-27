<template>
  <div id="app">
    <label for="numero1">Número 1:</label>
    <input type="number" v-model="numero1" @input="calcular" id="numero1">

    <label for="operacao">Operação:</label>
    <select v-model="operacao" @change="calcular" id="operacao">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
    </select>

    <label for="numero2">Número 2:</label>
    <input type="number" v-model="numero2" @input="calcular" id="numero2">

    <p>Resultado: {{ resultado }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: '+',
      resultado: 0,
    };
  },
  methods: {
    calcular() {
      switch (this.operacao) {
        case '+':
          this.resultado = this.numero1 + this.numero2;
          break;
        case '-':
          this.resultado = this.numero1 - this.numero2;
          break;
        case '*':
          this.resultado = this.numero1 * this.numero2;
          break;
        case '/':
          this.resultado = this.numero1 / this.numero2;
          break;
        default:
          this.resultado = 0;
      }
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
