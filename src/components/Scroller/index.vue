<template>
    <div class="wrapper" ref="wrapper">
        <slot></slot>
    </div>
</template>

<script>
import BScroll from 'better-scroll';

export default {
    name : 'Scroller',
    props:{
        handleToScroller:{
        type : Function,
        default : function(){}
        },
        handleToTouchEnd:{
            type : Function,
            default : function(){}
        }

        
    },
    mounted(){
        
        
        var scroll = new BScroll(this.$refs.wrapper,{
            tap : true,
            probeType:1
        });
        this.scroll = scroll;
        
        // console.log(scroll);
        scroll.on('scroll',(pos)=>{
            
            this.handleToScroller(pos)
        });
        scroll.on('touchEnd',(pos)=>{
            
            // console.log(this.handleToTouchEnd(pos));
            this.handleToTouchEnd(pos);
        });

    },
    methods :{
        
        toScrollTop(y){
            this.scroll.scrollTo(0,y);
        }
        
    }
    // updated(){
    //     var scroll = new BScroll(this.$refs.wrapper,{
    //         tap : true,
    //         probeType:1
    //     });
    // }
}
</script>

<style scoped>
.wrapper{height: 100%;}
</style>