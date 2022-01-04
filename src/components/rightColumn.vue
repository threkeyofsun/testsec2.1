<template>
  <div>
    <h4><span v-if="$store.state.value == ''">1</span>
        <span v-else>{{ $store.state.value }}</span>
        <br>
        <span>{{ $store.state.prime }}</span>
        </h4>
  </div>
</template>

<script>
export default {
  data() {
    return {
      output: "Heelo",
    };
  },
  props: ["value"],
};
</script>

<style lang="css" scoped></style>
