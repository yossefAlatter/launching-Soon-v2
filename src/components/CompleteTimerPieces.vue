<template>
  <div id="complete-timer-pieces">
    <div class="d-flex algin-items-center">
      <div class="mr-4" style="position:relative">
        <div class="days">
          <!-- create Timer Dom area -->
          <!-- start -->
          <div class="counter-con shadow"></div>
          <!-- end -->
        </div>
        <div class="sub">Days</div>
      </div>
      <div class="mr-4" style="position:relative">
        <div class="hours">
          <!-- create Timer Dom area -->
          <!-- start -->
          <div class="counter-con shadow"></div>
          <!-- end -->
        </div>
        <div class="sub">Hours</div>
      </div>
      <div class="mr-4" style="position:relative">
        <div class="minutes">
          <!-- create Timer Dom area -->
          <!-- start -->
          <div class="counter-con shadow"></div>
          <!-- end -->
        </div>
        <div class="sub">minutes</div>
      </div>
      <div style="position:relative">
        <div class="seconds">
          <!-- create Timer Dom area -->
          <!-- start -->
          <div class="counter-con shadow"></div>
          <!-- end -->
        </div>
        <div class="sub">seconds</div>
      </div>
    </div>
  </div>
</template>

<script>

//== import jquery ==//
//== start ==//
import $ from 'jquery'
//== end ==//

export default {
  name: "CompleteTimerPieces",

  data() {
    return {
      days: localStorage.getItem("days")?localStorage.getItem("days"):8,
      hours: localStorage.getItem("hours")?localStorage.getItem("hours"):23,
      mins: localStorage.getItem("mins")?localStorage.getItem("mins"):55,
      seconds: localStorage.getItem("seconds")?localStorage.getItem("seconds"):41,
    };
  },

  methods: {
    //== method to create Dom of timer ==//
    //== start ==//
    createTimerDom(counter, selector) {
        if(selector == `.hours .counter-con`){
            $(selector).html(`
                <div class="parent">
                    <div class="layer1">
                        <div class="num1">${(counter == 0)?23:counter -1}</div>
                    </div>
                    <div class="layer2">
                        <div class="cover"></div>
                        <div class="num2">${counter}</div>
                    </div>
                </div>
                <div class="layer3">
                    <div class="cover"></div>
                    <div class="num3">${(counter == 0)?23:counter -1}</div>
                </div>
                <div class="layer4">
                    <div class="num4">${counter}</div>
                </div>
            `);
        }else{
            $(selector).html(`
                <div class="parent">
                    <div class="layer1">
                        <div class="num1">${(counter == 0)?59:counter -1}</div>
                    </div>
                    <div class="layer2">
                        <div class="cover"></div>
                        <div class="num2">${counter}</div>
                    </div>
                </div>
                <div class="layer3">
                    <div class="cover"></div>
                    <div class="num3">${(counter == 0)?59:counter -1}</div>
                </div>
                <div class="layer4">
                    <div class="num4">${counter}</div>
                </div>
            `);

        }
    },
    //== end ==//

    //== method to make flip animation ==//
    //== start ==//
    creatFlipAnimation(selector) {
      $(selector).css({
        transition: "all 0.9s",
        "transition-timing-function": "ease-in-out",
        transform: "rotate3d(1, 0, 0, -180deg)",
      });
      $('.ly2').css({
        "transition": "all 1s",
        "transform": `translateY(-50%) scale(3.95) rotate(${(60-this.seconds)*-1}deg)`
      })
    },
    //== end ==//

    //== method to reset animation to zero point ==//
    //== start ==//
    goToZeroPoint(selector) {
      $(selector).css({
        transition: "all 0s",
        transform: "rotate3d(1, 0, 0, 0deg)",
      });
    },
    //== end ==//

    //== method to lanuch timer down ==//
    //== start ==//
    launchTimerDown(counter, selector) {
      this.creatFlipAnimation(`${selector} .parent`);
      setTimeout(() => {
        this.createTimerDom(counter, `${selector} .counter-con`);
        this.goToZeroPoint(`${selector} .parent`);
      }, 900);
    },
    //== end ==//
  },

  mounted() {

    //== timer count down working functionality ==//
    //== start ==//
    this.createTimerDom(this.days, `.days .counter-con`);
    this.createTimerDom(this.hours, `.hours .counter-con`);
    this.createTimerDom(this.mins, `.minutes .counter-con`);
    this.createTimerDom(this.seconds, `.seconds .counter-con`);

    var timer = setInterval(() => {
        
      if (this.seconds == 0) {
        if (this.mins == 0) {
          if (this.hours == 0) {
            if (this.days == 0) {
              $('.app-head').fadeOut();
              $('.app-head').css("color","var(--color2)");
              $('.app-head').html('we had launched');
              $('.app-head').fadeIn(1000);
              clearInterval(timer)
            } else {
              this.launchTimerDown(--this.days,'.days');
              this.hours = 24;
            }
          } else {
            this.launchTimerDown(--this.hours,'.hours');
            this.mins = 60;
          }
        } else {
          this.launchTimerDown(--this.mins,'.minutes');
          this.seconds = 60;
        }
      } else {
        this.launchTimerDown(--this.seconds,'.seconds');
      }

      localStorage.setItem("days",this.days)
      localStorage.setItem("hours",this.hours)
      localStorage.setItem("mins",this.mins)
      localStorage.setItem("seconds",this.seconds)

    }, 1000);
    //== end ==//

  },
};
</script>

<style lang="scss" scoped>

//== sub style ==//
.sub{
  color: var(--natureColor);
  text-align: center;
  font-weight: 500;
  text-transform: uppercase;
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  margin-top: 10px;
  letter-spacing: 3px;
}

//== completes-timer-pieces media ==//
//== start ==//
@media screen and (max-width: 800px){
  #complete-timer-pieces{
    transform: scale(0.95);
  }
}
@media screen and (max-width: 750px){
  #complete-timer-pieces{
    transform: scale(0.9);
  }
}
@media screen and (max-width: 700px){
  #complete-timer-pieces{
    transform: scale(0.85);
  }
}
@media screen and (max-width: 650px){
  #complete-timer-pieces{
    transform: scale(0.8);
  }
}
@media screen and (max-width: 600px){
  #complete-timer-pieces{
    transform: scale(0.75);
  }
}
@media screen and (max-width: 550px){
  #complete-timer-pieces{
    transform: scale(0.7);
  }
}
@media screen and (max-width: 500px){
  #complete-timer-pieces{
    transform: scale(0.65);
  }
}
@media screen and (max-width: 460px){
  #complete-timer-pieces{
    transform: scale(0.6);
  }
}
@media screen and (max-width: 430px){
  #complete-timer-pieces{
    transform: scale(0.55);
  }
}
@media screen and (max-width: 393px){
  #complete-timer-pieces{
    transform: scale(0.5);
  }
}
@media screen and (max-width: 340px){
  #complete-timer-pieces{
    transform: scale(0.41);
  }
}
@media screen and (max-width: 285px){
  #complete-timer-pieces{
    transform: scale(0.34);
  }
}
//== end ==//
</style>