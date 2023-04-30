<template>
    <button id="help"><img src="/help.png" alt=""></button>
</template>
<style scoped>
img{
    width: 1vw;
}
    #help{
        color: white;
        position: fixed;
        top: 6vw;
        left: 2.5vw;
        width: 10vw;
        text-align: left;
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }
    #help:hover::after{
        content: " - click the option you think has the most deaths";
    }
</style>