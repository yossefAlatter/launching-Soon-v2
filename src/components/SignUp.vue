<template>
    <div id="sign-up">
        
        <!-- sign up form -->
        <!-- start -->
        <form action="#">

            <div class="d-flex align-items-center">

                <div class="email-con mr-5">
                    <input type="email" name="email" id="email" placeholder="Your email..">
                </div>

                <button class="sign-btn">Sign Up</button>

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

//== style of input ==//
//== start ==//
.email-con input {
    border-radius: 10px;
    border: 2px solid var(--natureColor);
    max-width: 100%;
    width: 352px;
    padding: 15px;
    outline: none;
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