<template>
  <div id="app">
    <additional-fees :fees="fees" />
  </div>
</template>

<script>
import AdditionalFees from './components/AdditionalFees.vue';
export default {
  name: 'App',
  components: {
    AdditionalFees
  },
  data() {
    return {
      fees: [
        {
          id: 1,
          description: 'one',
          dollarAmount: 2.54,
          percentageAmount: 0,
          startDate: '',
          endDate: ''
        },
        {
          id: 2,
          description: 'two',
          dollarAmount: 2.54,
          percentageAmount: 0,
          startDate: '',
          endDate: ''
        },
        {
          id: 3,
          description: 'three',
          dollarAmount: 2.54,
          percentageAmount: 0,
          startDate: '',
          endDate: ''
        }
      ]
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
