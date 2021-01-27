<template>
  <div id="app">

    <!-- AppBg -->
    <my-bg-app />
    <!-- start -->

    <!-- end -->

    <div class="face d-flex flex-column justify-content-center">
    <!-- IntroPragraph -->
    <!-- start -->
    <intro-pragraph />
    <!-- end -->

    <!-- complete-timer-pieces -->
    <!-- start -->
    <complete-timer-pieces />
    <!-- end -->

    <!-- sign up -->
    <!-- start -->
    <sign-up />
    <!-- end -->

    </div>

  </div>
</template>

<script>

//== import my components ==//
//== start ==//
import CompleteTimerPieces from './components/CompleteTimerPieces.vue'
import IntroPragraph from './components/IntroPragraph.vue'
import MyBgApp from './components/myBgApp.vue'
import SignUp from './components/SignUp.vue'
//== end ==//

export default {
  name: 'App',
  components: {
    CompleteTimerPieces,
    IntroPragraph,
    SignUp,
    MyBgApp,
  }
}

</script>

<style lang="scss">

//== app style ==//
//== start ==//
#app{
  position: relative;
  height: 100vh;
}
//== end ==//

//== face style ==//
//== start ==//
.face{
  padding-left: 130px;
  height: 100%;
  position: relative;
  z-index: 999;
}
//== end ==//

//== face media ==//
//== start ==//
@media screen and (max-width: 1100px){
  .face{
    padding: 0;
    margin: 0 auto;
    display: flex;
    align-items: center;
  }
}
//== end ==//

</style>
