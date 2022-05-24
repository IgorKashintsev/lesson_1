<template>
  <div>
    <div class="main">
      <input type="number" v-model.number="op1">
      <input type="number" v-model.number="op2">
      = {{result}}
    </div>
    <div>
      <button @click="sum">+</button>
      <button @click="sub">-</button>
      <button @click="div">/</button>
      <button @click="mult">*</button>
      <button @click="expon">*ex</button>
      <button @click="divInteger">/in</button> 
    </div>
  </div>
</template>

<script>
export default {
  name: 'CalcComponent',
  data() {
    return {
      op1: 0,
      op2: 0,
      result: 0,
    }
  },
  methods: {
    sum() {
      this.result = this.op1 + this.op2;
    },
    sub() {
      this.result = this.op1 - this.op2;
    },
    div() {
      this.result = this.op1 / this.op2;
    },
    mult() {
      this.result = this.op1 * this.op2;
    },
    expon() {
      this.result = Math.pow(this.op1, this.op2);
    },
    divInteger() {
      this.result = (this.op1 - this.op1 % this.op2)/this.op2;
    }
  }
}
</script>

<style scoped>

</style>