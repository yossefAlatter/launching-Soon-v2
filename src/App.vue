<template>
  <div id="app">
    <!-- sign-btns -->
    <!-- start -->
    <div class="btns-con">
      <button class="btn-login ">Log in</button>
      <button class="btn-signup ">Sign Up</button>
    </div>
    <!-- end -->

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
  padding: 20px
}
//== end ==//

//== sign btns style ==//
//== start ==//
.btns-con{
  position: absolute;
  top: 0;
  right: 0;
  z-index: 999;
  padding-top: 20px;
  padding-right: 20px;
  margin-bottom: 20px;
}
.btn-login , .btn-signup{
  border: none;
  outline: none;
  padding: 15px;
  width: 130px;
  border-radius: 10px;
  font-weight: 700;
  position: relative;
  z-index: 999;
  cursor: pointer;
  &:hover{
    transition: 0.3s;
    opacity: 0.8;
  }
}
.btn-login{
  background-color: transparent;
  color:var(--natureColor);
}
.btn-signup{
  background-color: var(--natureColor);
  color: white;
}
//== end ==//

//== face style ==//
//== start ==//
.face{
  padding-left: 130px;
  height: 100%;
  position: relative;
  z-index: 997;
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
