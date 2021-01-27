<template>
    <div id="intro-pragraph">

        <!-- heading -->
        <!-- start -->
        <h2 class="heading">
            We are launching in
        </h2>
        <!-- end -->

        <!-- subText -->
        <!-- start -->
        <p class="sub-text">
            A scocial betting network where you can follow tipsters, share and copy bets from our community &amp; friends.
        </p>
        <!-- end -->

    </div>
</template>

<script>

export default {
    name: 'IntroPragraph',
}

</script>

<style lang="scss" scoped>
//== intro-pragraph style ==//
#intro-pragraph{
    position: relative;
    cursor: default;
}
//== start ==//

//== end ==//

//== heading style ==//
//== start ==//
.heading{
    color: var(--mainColor);
    font-weight: 700;
    font-size: 4.2em;
    margin-bottom: 25px;
    cursor: default;
    width: fit-content;
    &:hover{
        transition: 0.3s;
        color: (var(--natureColor));
    }
}
//== end ==//

//== sub-text-style ==//
//== start ==//
.sub-text{
    color: var(--subColor);
    font-weight: 400;
    font-size: 1.4em;
    max-width: 651px;
    margin-bottom: 25px;
    cursor: default;
}
//== end ==//

</style>