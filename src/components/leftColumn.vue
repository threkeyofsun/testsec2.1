<template>
  <div class="overflow-auto">
    <input
      v-model.number="output"
      type="number"
      oninput="if(this.value < 0) this.value = 1;"
      min="0"
      class="form-control p-0 inputNum"
      
    />
    <span v-if="output !== '' && output > 0 ? myFunction() : ''"></span>
  </div>
  <button v-on:click="fibonacciSequence()">Clickme!</button>
  <!-- {{ fibonacci }} -->
  <span v-for="n in fibonacci">
    <span v-if="output == n ? (resultI = true) : (resultI = false)">
      {{ resultI }}
    </span>
  </span>
</template>

<script>
// import RightCol from "./rightColumn.vue";

export default {
  components: {
    //   RightCol
  },
  data() {
    return {
      output: "0",
      myNumber: "",
      formattedNumber: "",
      isPrime: true,
      fibonacci: [],
      resultI: true,
    };
  },
  methods: {
    myFunction: function () {
      this.$store.state.value = this.output.toFixed(0);
    },
    fibonacciSequence: function (e) {
      var i;
      var fib = [];
      var result = [];
      var number = this.output + 2;

      fib[0] = 0;
      fib[1] = 1;
      for (i = 2; i < number; i++) {
        // Next fibonacci number = previous + one before previous
        fib[i] = fib[i - 2] + fib[i - 1];
        result.push(fib[i]);
      }
      result.unshift(1);
      result.unshift(0);
      this.fibonacci = result;
    },
  },
};
</script>

<style lang="css" scoped>
.inputNum {
  width: 70%;
  border-radius: 0%;
}
</style>
