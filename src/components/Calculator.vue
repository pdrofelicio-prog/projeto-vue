<template>
  <div>
    <input type="number" v-model.number="num1" placeholder="Enter first number" />
    <input type="number" v-model.number="num2" placeholder="Enter second number" />
    
    <select v-model="operation">
      <option value="add">+</option>
      <option value="subtract">-</option>
      <option value="multiply">*</option>
      <option value="divide">/</option>
    </select>
    
    <h2>Result: {{ result }}</h2>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operation: 'add',
    };
  },
  computed: {
    result() {
      switch (this.operation) {
        case 'add':
          return this.num1 + this.num2;
        case 'subtract':
          return this.num1 - this.num2;
        case 'multiply':
          return this.num1 * this.num2;
        case 'divide':
          return this.num2 !== 0 ? this.num1 / this.num2 : 'Cannot divide by zero';
      }
    },
  },
};
</script>

<style scoped>
input {
  margin-right: 10px;
}
</style>