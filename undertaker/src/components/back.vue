<template>
    <RouterLink to="/">
        <button id="back">
            <img id="skull" src="/skull.png" alt="">
        </button>
    </RouterLink>
</template>
<style scoped>
#skull{
    width: 4vw;
}
    #back{
        color: white;
        position: fixed;
        top: 1vw;
        left: 1vw;
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }
    #back:hover::after{
        content: " - go back";
    }
</style>