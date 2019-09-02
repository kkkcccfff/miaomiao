<template>
    
    <div class="box" @touchend='touchend' @touchstart='touchstart' :class="{'box-hover':ishover}">
        正在加载...
    <div class="loader-12" :class="{'box-loader':ishover}"></div>
</div>

</template>

<script>
export default {
    name : 'Loading',
    data(){
        return {
            ishover:false
        }
    },
    methods:{
        
        touchend(){
            this.ishover=false;
        },
        touchstart(){
            
            this.ishover = true;
        }
        
    }
}
</script>

<style scoped>

.box {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
    line-height: 200px;
    display: block;
    width: 200px;
    height: 200px;
    /* border: 1px solid currentcolor; */
    border-radius: 3px;
    font-size: 30px;
    color: rgba(200, 200, 200, 0.5);
    /* padding: 1em; */
    margin-bottom: .25em;
    -webkit-transition: .3s color, .3s border;
    transition: .3s color, .3s border;
}
/* .box:hover {
    color: #d60b52;
    font-size: 0;
    padding: 0;
    /* border-width: 3px; */
    /* line-height: 200px; */
/* }  */
.box-hover {
    color: #d60b52;
    font-size: 0;
    padding: 0;
    /* border-width: 3px; */
    line-height: 200px;
}
/* .box:hover [class*="loader-"] {
    font-size: 70px;
    line-height: 200px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
} */
.box-loader{
    font-size: 70px;
    line-height: 200px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
}
[class*="loader-"] {
    display: inline-block;
    width: 1em;
    height: 1em;
    color: inherit;
    vertical-align: middle;
    pointer-events: none;
}
.loader-12 {
    position: relative;
}
.loader-12:before,
.loader-12:after {
    content: '';
    display: block;
    position: absolute;
    background-color: currentcolor;
    left: 50%;
    right: 0;
    top: 0;
    bottom: 50%;
    box-shadow: -.5em 0 0 currentcolor;
    -webkit-animation: loader-12 1s linear infinite;
    animation: loader-12 1s linear infinite;
}
.loader-12:after {
    top: 50%;
    bottom: 0;
    -webkit-animation-delay: .25s;
    animation-delay: .25s;
}
@-webkit-keyframes loader-12 {
    0%, 100% {
        box-shadow: -.5em 0 0 transparent;
        background-color: currentcolor;
    }
    50% {
        box-shadow: -.5em 0 0 currentcolor;
        background-color: transparent;
    }
}
@keyframes loader-12 {
    0%, 100% {
        box-shadow: -.5em 0 0 transparent;
        background-color: currentcolor;
    }
    50% {
        box-shadow: -.5em 0 0 currentcolor;
        background-color: transparent;
    }
}
</style>