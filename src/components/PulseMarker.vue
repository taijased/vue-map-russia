<template>
    <div class="pulse-marker" :style="{ top: pointY + 'px', left: pointX + 'px' }">
        <div class="pulse">
        </div>
        <div class="circle"></div>
    </div>
</template>
<script>
export default {
  props: {
    pointX: Number,
    pointY: Number
  }
};
</script>

<style lang="less">
@pulse-size: 50px;
@ring-size: 20px;
@boreder-ring-size: 5px;
@circle-size: 10px;
.pulse-marker {
  position: absolute;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  width: @pulse-size;
  height: @pulse-size;
  bottom: 0;
  right: 0;
  .pulse {
    width: @ring-size;
    height: @ring-size;
    border: @boreder-ring-size solid #ef5350;
    border-radius: 50%;
    animation: pulse 1s ease-out infinite;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
  }
  .circle {
    width: @circle-size;
    height: @circle-size;
    border-radius: 50%;
    margin-left: -40%;
    background: #ef5350;
  }
}
@keyframes pulse {
  0% {
    -webkit-transform: scale(0);
    opacity: 0;
  }

  25% {
    -webkit-transform: scale(0.5);
    opacity: 0.1;
  }

  50% {
    -webkit-transform: scale(1);
    opacity: 0.3;
  }

  75% {
    -webkit-transform: scale(1.5);
    opacity: 0.5;
  }

  100% {
    -webkit-transform: scale(2);
    opacity: 0;
  }
}
</style>
