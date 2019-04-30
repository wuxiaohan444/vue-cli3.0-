<template>
    <div id="app">
        <div class="box">
            <div style="background: yellow"></div>
            <div></div>
            <div style="background: darkturquoise"></div>
        </div>
    </div>
</template>

<script>

    export default {
        name: 'app',

    }
</script>

<style lang="less">
    *{
        padding: 0;
        margin: 0;
    }
    #app {
        .box {
            margin: 0 auto;
            width: 750px;
            height: 600px;
            background: blue;
            display: flex;
            div{
                flex: 1;
            }
        }
    }
</style>
