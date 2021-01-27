<template>
  <div class="bg">
    <div class="ly1"></div>
    <div class="ly2">
      <div class="clock-cover"></div>
      <div class="clock"></div>
    </div>
    <div class="ly3"></div>
  </div>
</template>

<script>
export default {
  name: "myBgApp",

  mounted() {
    var clockElement = document.querySelector(".clock");
    for (let i = 1; i <= 30; i++) {
      clockElement.innerHTML += `<div class="num${i} num"></div>`;
      document.querySelector(`.num${i}`).style.transform = `rotate(${6 *
        i}deg) translateY(-50%)`;
    }
  },
};
</script>

<style lang="scss" scoped>
//== bg style ==//
//== start ==//
.bg {
  position: absolute;
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  height: 100vh;
  overflow: hidden;
}
.ly1 {
  position: absolute;
  height: 100%;
  width: 100%;
  background-color: var(--bgColor);
  z-index: 1;
}

//== clock style ==//
//== start ==//
.ly2 {
  position: absolute;
  top: 50%;
  transform: translateY(-50%) scale(3.95);
  background-color: white;
  border-radius: 50%;
  width: 500px;
  height: 500px;
  z-index: 5;
  overflow: hidden;
  animation-name: rotateClock;
  animation-duration: 60s;
  animation-iteration-count: infinite;
  animation-fill-mode: both;
  animation-timing-function: ease-in-out;
  .clock-cover {
    border-radius: 50%;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: white;
    z-index: 7;
    width: 480px;
    height: 480px;
  }
  .clock {
    width: 98%;
    height: 98%;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
}
//== end ==//

.ly3 {
  position: absolute;
  top: -62px;
  left: -182px;
  border-radius: 50%;
  background-color: var(--bgColor);
  width: 768px;
  height: 700px;
  z-index: 10;
}

//== end ==//

//== bg media ==//
//== start ==//

@for $i from 1540 through 1000 {
  @media screen and (max-width:#{$i}px) {
    .ly2{
      $i: 500 * ($i/1540);
      min-width: #{$i}px;
      max-width: #{$i}px;
      min-height: #{$i}px;
      max-height: #{$i}px;
    }
    .clock-cover{
      $i: $i - 20;
      min-width: #{$i}px;
      max-width: #{$i}px;
      min-height: #{$i}px;
      max-height: #{$i}px;
    }
  }
}

//== end ==//
</style>
