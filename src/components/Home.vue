<template>
     <div class="wrapper" @click="goEvent($event)">
       <div class="wrapper-title">{{msg}}</div>
       <RussianMap/>
       <v-dialog/>
       <PulseMarker v-if="x && y" :pointX="x" :pointY="y"/>
     </div>
</template>

<script>
import RussianMap from "./RussianMap";
import PulseMarker from "./PulseMarker";

export default {
  props: {
    msg: String
  },
  data() {
    return {
      x: null,
      y: null
    };
  },
  methods: {
    goEvent(event) {
      this.x = event.x - 25;
      this.y = event.y - 25;
    }
  },
  components: {
    RussianMap,
    PulseMarker
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
