<template>
  <div class="ring" :style="{ color, width: size, height: size }">
    Loading
    <span></span>
  </div>
</template>

<script lang="ts">
export default {
  props: {
    size: { type: String, default: '64px' },
    color: { type: String, default: '#3eaf7c' },
  },
};
</script>

<style scoped>
.ring {
  position: relative;
  background: transparent;
  border: 3px solid #afafaf;
  border-radius: 50%;
  text-align: center;
  line-height: 150px;
  font-family: sans-serif;
  font-size: 20px;
  letter-spacing: 4px;
  text-transform: uppercase;
  text-shadow: 0 0 10px #3eaf7c;
}
.ring:before {
  content: '';
  position: absolute;
  top: -3px;
  left: -3px;
  width: 100%;
  height: 100%;
  border: 3px solid transparent;
  border-top: 3px solid #3eaf7c;
  border-right: 3px solid #3eaf7c;
  border-radius: 50%;
  animation: animateC 2s linear infinite;
}
span {
  display: block;
  position: absolute;
  top: calc(50% - 2px);
  left: 50%;
  width: 50%;
  height: 4px;
  background: transparent;
  transform-origin: left;
  animation: animate 2s linear infinite;
}
span:before {
  content: '';
  position: absolute;
  width: 16px;
  height: 16px;
  border-radius: 50%;
  background: #3eaf7c;
  top: -6px;
  right: -8px;
}
@keyframes animateC {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
@keyframes animate {
  0% {
    transform: rotate(45deg);
  }
  100% {
    transform: rotate(405deg);
  }
}
</style>
