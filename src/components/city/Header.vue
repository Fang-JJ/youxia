<template>
    <header>
        选择城市
        <i class="iconfont" @click="toHome">X</i>
    </header>
</template>
<script>
export default {
    methods:{
        toHome(){
            this.$router.push({
                path:"/"
            })
        }
    }
}
</script>
<style scoped>
    header{
        width: 100%;
        height: 1.173rem;
        line-height: 1.173rem;
        font-size: .4rem;
        color: #333;
        font-weight: 700;
        text-align: center;
        background-color: #fed101;
    }
    header i{
        position: absolute;
        right: .3rem;
        font-weight: 700;
    }

</style>