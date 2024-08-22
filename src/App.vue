<template>
  <div id= "app">
    <div class= "calculadora">
      <div class="input-container">
        <input v-model.number = "numero1" type= "number" placeholder= "Primeiro número" />
        <select v-model= "operacao">
          <option value="+">+</option>
          <option value="-">-</option>
          <option value="*">*</option>
          <option value="/">/</option>
        </select>
        <input v-model.number= "numero2" type= "number" placeholder= "Segundo número" />
      </div>
      <div class="resultado">
        Resultado: {{ resultado }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: '+',
    };
  },


  computed: {
    resultado() {
      switch (this.operacao) {
        case '+':
          return this.numero1 + this.numero2;
        case '-':
          return this.numero1 - this.numero2;
        case '*':
          return this.numero1 * this.numero2;
        case '/':
          return this.numero1 / this.numero2;
        default:
          return 0;
      }
    }
  }
};
</script>


<style>

</style>
