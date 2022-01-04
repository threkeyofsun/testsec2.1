<template>
  <div class="home">
    <div class="wrapRow">
      <div class="leftCol border"><leftColumn /></div>
      <div class="midCol flex-grow-1 border"><midCol /></div>
      <div class="rightCol border"><rightCol /></div>
    </div>
    <!-- <AccountInfo/> -->
  </div>
  <div>
    
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
    AccountInfo
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
.wrapRow{
  display: flex;
}

/* Breakpoint responsive */
@media only screen and (max-width: 600px) {
  .wrapRow{
   height: 2000px;
   overflow-y: scroll;
}
}
</style>
