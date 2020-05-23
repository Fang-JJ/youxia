<template>
    <div class="scroll">
        <div class="scroll-content">
            <div class="scroll-right">
                <ul :class="{animatedTop}">
                    <li v-for="item in scrollList" :key="item.id">
                        <img src="@/assets/img/scroll.png" alt="">
                        {{item.title}}
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return {
            animatedTop:false,
            scrollList:[
                {
                    id:0,
                    title:"清迈旅客落地签如何搞定？带你了解泰北小城清迈"
                },
                {
                    id:1,
                    title:"带你了解泰北小城清迈"
                },
                {
                    id:2,
                    title:"清迈旅客落地签如何搞定？带你了解泰北小城清迈"
                },
                {
                    id:3,
                    title:"清迈旅客落地签如何搞定？带你了解泰北小城清迈"
                },
                {
                    id:4,
                    title:"清迈旅客落地签如何搞定？带你了解泰北小城清迈"
                },
                {
                    id:5,
                    title:"清迈旅客落地签如何搞定？带你了解泰北小城清迈"
                },
                {
                    id:6,
                    title:"清迈旅客落地签如何搞定？带你了解泰北小城清迈"
                }
            ]
    }
},
            methods:{
                showScroll(){
                    this.animatedTop=true;
                    setTimeout(() => {
                        this.scrollList.push(this.scrollList[0]);
                        this.scrollList.shift();
                        this.animatedTop=false; 
                    }, 500)
                }
            },
            mounted(){
                setInterval(this.showScroll,2000);
            }
        }
</script>

<style scoped>
    .animatedTop{
        transition: all .5s;    
        margin-top: -0.66666666rem;
    }
    .scroll{
        padding: .3rem 0;
        margin-top: 0;
    }
    .scroll-content{
        background-image: url("http://localhost:8080/img/scroll.png");
        background-size: 100%;
        width:100%;
        height: 1.3333333333rem; 
        position: relative;
    }
    .scroll-right{
        position: absolute;
        right: 0;
        width: 8.133333333rem;
        height: 1.3333333333rem;
        overflow: hidden;
    }
    li{
        font-size: .35rem;
        color:#333;
        line-height:.666666666rem;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
    }
</style>