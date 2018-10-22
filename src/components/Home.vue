<template>
     <div class="wrapper">
       <div class="wrapper-title">{{msg}}</div>
       <RussianMap/>
       <v-dialog/>
     </div>
</template>

<script>
import RussianMap from "./RussianMap";

export default {
  props: {
    msg: String
  },
  components: {
    RussianMap
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less">
* {
  margin: 0;
  padding: 0;
}
.wrapper {
  margin: 0;
  height: 100%;
  overflow: hidden;
  .wrapper-title {
    position: absolute;
    margin-left: auto;
    margin-right: auto;
    left: 0;
    right: 0;
    font-size: 72px;
    z-index: 2;
    -moz-user-select: none;
    -khtml-user-select: none;
    user-select: none;     
  }
}
</style>
