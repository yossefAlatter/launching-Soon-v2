<template>
    <div id="sign-up">
        
        <!-- sign up form -->
        <!-- start -->
        <form action="#">

            <div class="d-flex align-items-center justify-content-center justify-content-lg-start flex-column flex-lg-row w-100">

                <div class="email-con mr-0 mr-lg-5">
                    <input type="email" name="email" id="email" placeholder="Your email..">
                </div>

                <button class="sign-btn mt-3 mt-lg-0">Sign Up</button>

            </div>

        </form>
        <!-- end -->

    </div>
</template>

<script>

export default {
    name: 'SignUp',

}

</script>

<style lang="scss" scoped>

//== sign-up style ==//
//== start ==//
#sign-up{
    position: relative;
    margin-top: 50px;
}
//== end ==//

//== sign-up media ==//
//== start ==//
@media screen and (max-width: 400px) {
    #sign-up{
    min-width: 100%;
    max-width: 100%;
    *{
      min-width: 100%;
    max-width: 100%;  
    }
}

}
@media screen and (max-width: 360px) {
    #sign-up{
    margin-top: 0px;}
}
//== end ==//

//== style of input ==//
//== start ==//
.email-con input {
    border-radius: 10px;
    border: 2px solid var(--natureColor);
    max-width: 100%;
    min-width: 352px;
    padding: 15px;
    outline: none;
}
//== end ==//

//== media of input ==//
//== start ==//
@media screen and (max-width: 400px) {
    .email-con input{
    min-width: 100%;
    max-width: 100%;
}
}
//== end ==//

//== style of sign-btn ==//
//== start ==//
.sign-btn{
    background-color: #57C57F;
    color: white;
    padding: 15px;
    width: 130px;
    border: none;
    outline: none;
    border-radius: 10px;
    &:hover{
        transition: 0.3s;
        opacity: 0.8;
    }
}
//== end ==//

</style>