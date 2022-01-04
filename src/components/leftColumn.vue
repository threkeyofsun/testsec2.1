<template>
  <div class="overflow-auto" >
    <input 
      v-model.number="output"
      type="number"
      oninput="if(this.value < 0) this.value = 1;"
      min="0"
      class="form-control p-0 inputNum"  
    />
<span v-if="output !== '' && output > 0 ? myFunction() : ''"></span>
<!-- <right-col :value=formattedNumber /> -->
  </div>
</template>

<script>
// import RightCol from "./rightColumn.vue";

export default {
  components: {
    //   RightCol
  },  
  data() {
    return {
      output: "",
      myNumber:'',
	    formattedNumber:'',
      isPrime:true
    };
  },
  methods:{
    myFunction: function () {		
		this.$store.state.value = this.output.toFixed(0);
    },
    fibonancy:function(){
      
    }

   }
};
</script>

<style lang="css" scoped>
.inputNum {
  width: 70%;
  border-radius: 0%;
}
</style>
