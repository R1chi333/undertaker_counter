<template>
    <button id="help">DUMMY</button>
</template>
<style scoped>
    #help{
        color: white;
        position: fixed;
        top: 3vw;
        left: 1vw;
    }
    #help:hover::after{
        content: " - just click the option you think has the most deaths";
    }
</style>