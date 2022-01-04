<template>
  <div>
       <button v-on:click="isPrime()">Add 1</button> {{forprime}}
    <select @change="switchSelect($event)" class="dropdown-toggle">
      <option class="item" :value="$store.state.prime" selected>isPrime</option>
      <option class="item" :value="!$store.state.prime" >IsFibanacci</option>
      
    </select>
  
<p>Your choice is: {{selected}}</p>
<p>answer {{answer}}</p>
<span v-if="selected == true" >{{this.$store.state.value%2}}</span>
  </div>
</template>

<script>
export default {
  data() {
    return {
        counter: 0,
        answer:'',
        selected: 'isPrime',
        forprime:'as',
    };
  },
  methods:{
      isPrime:function () {
          if(this.$store.state.value%2 == 1){
    alert("true");
    // this.answer == 'true';
          }else{ alert("false");}
       
        // this.forprime == 
      },
      switchSelect(event) {
      this.selected = event.target.value;
      if (this.selected == 'isPrime') {
          this.answer == this.$store.state.value;
          console.log(this.$store.state.value%2);
          this.answer = 'หารสอง'
      }else{
           this.answer = 'bpoo'
      }
    }
  }
};
</script>

<style lang="css" scoped>
option{
    font-size: 16px;
    background: white;
}

</style>
