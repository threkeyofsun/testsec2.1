<template>
  <div class="home">
    <div class="wrapRow">
      <div class="leftCol border">
        <div class="overflow-auto">
          <input
            v-model.number="output"
            type="number"
            step="1"
            oninput="if(this.value < 0) this.value = 1;"
            min="0"
            class="form-control p-0 inputNum"
          />
          <span v-if="output !== '' && output > 0 ? myFunction() : ''"></span>
        </div>
        <!--  -->
      </div>
      <!-- Middle Column -->
      <div class="midCol flex-grow-1 border">
        <div>
          <select @change="switchSelect($event)" class="dropdown-toggle">
            <option class="item" selected>isPrime</option>
            <option class="item">IsFibanacci</option>
          </select>
        </div>
      </div>
      <!-- Right Col -->
      <div class="rightCol border">
        <h4>
          <span v-if="forprime === 'isPrime'">
            <span v-if="this.$store.state.value % 2 == 1">true</span>
            <span v-else>false</span>
          </span>
          <span v-else>
            <span v-for="n in fibonacci">
              <span class="fibo" v-if="this.$store.state.value == n ? (resultI = true) : (resultI = false)">
                {{ resultI }}
              </span>
            </span>
          </span>
        </h4>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import leftColumn from "../components/leftColumn.vue";
import rightCol from "../components/rightColumn.vue";
import midCol from "../components/middleColumn.vue";
import AccountInfo from "../components/AccountInfo.vue";

export default {
  name: "Home",
  components: {
    leftColumn,
    rightCol,
    midCol,
    AccountInfo,
  },
  data() {
    return {
      output: "0",
      myNumber: "",
      formattedNumber: "",
      isPrime: true,
      fibonacci: [],
      resultI: true,
      // Middle Col
      counter: 0,
      answer: "",
      selected: "isPrime",
      forprime: "isPrime",
      // Right Col
      optionValue: true,
    };
  },
  methods: {
    myFunction: function () {
      this.$store.state.value = this.output.toFixed(0);
    },

    // Middle Col
    isPrime: function () {
      if (this.$store.state.value % 2 == 1) {
        alert("true");
        // this.answer == 'true';
      } else {
        alert("false");
      }

      // this.forprime ==
    },
    switchSelect(event) {
      if (event.target.value === "isPrime") {
        // do your change
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
        return (this.forprime = "isPrime");
      }

      if (event.target.value === "IsFibanacci") {
        var i;
        var fib = [];
        var result = [];
        var number = this.output + 99;

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
        return (this.forprime = "IsFibanacci");
      }
    },
  },
};
</script>

<style lang="css" scoped>
.leftCol {
  width: 200px;
}
.midCol {
  min-width: 100px;
}
.rightCol {
  width: 300px;
}
.wrapRow {
  display: flex;
}
.inputNum {
  width: 70%;
  border-radius: 0%;
}
option {
  font-size: 16px;
  background: white;
}

/* Breakpoint responsive */
@media only screen and (max-width: 600px) {
  .wrapRow {
    height: 2000px;
    overflow-y: scroll;
  }
}
</style>
