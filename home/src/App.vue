<template>
  <div id="app">
    <header class="header">My personal costs</header>
   <!--  <img alt="Vue logo" src="./assets/logo.png">
    <Calc /> -->
    <AddPayment @add-payment="addNewPayment"/>
    <PaymentDisplay :items="paymentsList"/>
  </div>
</template>

<script>
// import Calc from './components/Calc.vue';
import PaymentDisplay from './components/PaymentDisplay.vue';
import AddPayment from './components/AddPaymentForm.vue';

export default {
  name: 'App',
  components: {
    // Calc,
    PaymentDisplay,
    AddPayment,
  },
  data() {
    return {
      paymentsList: [],
    };
  },
  methods: {
    fetchData() {
      return [
        {
          date: '28.03.2020',
          category: 'Food',
          value: 169,
        },
        {
          date: '24.03.2020',
          category: 'Transport',
          value: 360,
        },
        {
          date: '24.03.2020',
          category: 'Food',
          value: 532,
        },
      ];
    },
    addNewPayment(payment) {
      console.log('addNewPayment', payment);
      this.paymentsList.push(payment);
    },
  },
  created() {
    this.paymentsList = this.fetchData();
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 60px auto;
  max-width: 1000px;
}
.header {
font-size: 30px;
}
</style>
