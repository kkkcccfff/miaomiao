<template>
    <div id="main">
        <Header title='我的喵喵'/>
        <div id="content">
            <login/>
        </div>
        <TabBar/>
    </div>
</template>

<script>
import Header from '@/components/Header';
import TabBar from '@/components/Tabbar';
import login from '@/components/login'
export default {
    name:'mine',
    components:{
        Header,
        TabBar,
        login,
    }
}
</script>

<style scoped>

</style>

