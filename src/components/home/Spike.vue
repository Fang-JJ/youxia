<template>
    <div class="spike">
        <swiper :options="swiperOption">
            <div class="spike-content" @click="toDetail">
                <swiper-slide>
                <div class="spike-top">
                    <!-- 限时结束图片 -->
                    <img src="@/assets/img/spike1.png">
                    <!-- 倒计时 -->
                    <span>距离结束</span>
                    <span>10天</span>
                    <span>10</span>
                    <span>:</span>
                    <span>10</span>
                    <span>:</span>
                    <span>10</span>
                </div>
                <div class="spike-bottom">
                    <!-- 图片 -->
                    <img src="../../../public/img/spike2.jpg">
                    <div class="bottom-title">
                        <p>
                            开业特惠小城故事开业特惠小城故事开业特惠小城故事开业特惠小城故事开业特惠小城故开业特惠小城故事开业特惠小城故事开业特惠小城故事开业特惠小城故事开业特惠小城故开业特惠小城故事开业特惠小城故事开业特惠小城故事开业
                        </p>
                        <div class="bottom-price">
                            <span>
                                ￥99
                            </span>
                            <p>
                                剩下285个
                            </p>
                        </div>
                    </div>
                </div>
            </swiper-slide>
            </div>
            
            <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
        
    </div>
</template>

<script>
export default {
    data(){
        return{
            swiperOption:{
                pagination:{
                    el:".swiper-pagination"
                }
            }
        }
    },
    methods:{
        toDetail(){
            this.$router.push({
                path:"/detail"
            })
        }
    }
}
</script>

<style scoped>
    .spike{
        width:100%;
        height: 4.3777777rem;
    }
    .spike-content{
        padding:.3rem;
    }
    .spike-top {
        width: 100%;
        height: 1.29333333rem;
        display:flex;
        align-items: center;
        font-size: .32rem;
    }
    .spike-top img{
        height: .4133333rem;
        width:1.89333333rem;
    }
    .spike-top span {
        margin-left: .15rem;
    }
    .spike-bottom{
        justify-content: space-between;
        display:flex;
        
    }
    .spike-bottom img{
        width:3.093333rem;
        height: 2.12rem;
    }
    .spike-bottom .bottom-title{
        width:5.86rem;
        margin-left: none;
        
    }
    .spike-bottom .bottom-title p{
        line-height: .38rem;
        color:#333;
        display: -webkit-box;
        -webkit-box-orient: vertical;
        -webkit-line-clamp: 2;
        overflow:hidden;
        font-size: .35rem;
        text-align: center;
    }
    .bottom-price{
        margin-top: .6rem;
        display:flex;
        justify-content: space-between;
        font-size: .45rem;
    }
    .bottom-price span{
        display: block;
        padding-top: .1rem;
    }
    .bottom-price p{
        padding: .1rem;
        border:solid 1px #444;
        border-radius: .1rem;
        background-color: #fed101;
    }
    .swiper-container{
        overflow: visible;
    }
    .swiper-pagination >>>.swiper-pagination-bullet-active{
        background-color: orange;
    }
    .swiper-pagination-fraction,.swiper-pagination-custom,.swiper-container-horizontal>.swiper-pagination-bullets{
        bottom:-.8rem
    }
</style>