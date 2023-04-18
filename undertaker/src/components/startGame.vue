<template>
    <div>
        <div>
        <h1 id="title">UNDERTAKER<br/>COUNTER</h1>
        <img id="back" src="/coffin.png" alt="">
    </div>
    <RouterLink to="/game" id="startbutton">
        <img id="tomb" src="/tomb.png" alt="start button">
        <h2 id="start">START</h2>
    </RouterLink>
    </div>
</template>


<style scoped>
button{
    background-color: transparent;
    border: 0px;
}
#startbutton{
    width: 25vw;
    position: absolute;
    right: 18%;
    top: 52%;
    text-decoration: none;
}
#startbutton:hover{
    font-size: 150%;
    transition-duration: .3s;
}
#startbutton:not(hover){
    font-size: 130%;
    transition-duration: .3s;
}
h2{
    font-family: 'Bevan';
    font-style: normal;
    font-weight: 400;
    text-align: center;
    margin-top: -9.1vw;
    margin-right: .5vw;
    color: #272727;
    z-index: 3;
    transform: rotate(3.5deg);
}
#tomb{
    width: 25vw;
    position: relative;
}
#back{
    width: 50vw;
    margin: 0;
    position: absolute;
    top: 47%;
    left: 50%;
    transform: translate(-50%, -50%);
     z-index: 0;
}
h1{
    margin: 0;
    position: absolute;
    top: 49%;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 1;
    font-family: 'Barrio';
    font-style: normal;
    font-weight: 400;
    font-size: 6.5vw;
    text-align: center;
    color: #AC3434;
    text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
}
</style>

<script>
</script>