<template>
    <div class="banner">
        <transition 
            enter-active-class="bounceInLeft"
            leave-active-class="bounceOutLeft"
        >
            <div class="banner-left animated" v-show="toshow"></div>
        </transition>
        <div class="banner-header">
            <div class="banner-top">
                <div class="top-left" @click="toCity">
                    {{cityName}}
                    <i class="iconfont">&#xe6b0;</i>
                </div>
                <div class="top-search">
                    <i class="iconfont">&#xe6e4;</i>
                    泰国
                </div>
                <div class="top-right" @click="toShow">
                    <img src="@/assets/img/show.png" alt="">
                </div>
            </div>

            <div class="banner-swiper">
                <swiper :options="swiperOptions">
                    <swiper-slide>
                        <img src="@/assets/img/banner1.png" alt="">
                    </swiper-slide>
                    <swiper-slide>
                        <img src="@/assets/img/banner2.png" alt="">
                    </swiper-slide>
                    <swiper-slide>
                        <img src="@/assets/img/banner3.png" alt="">
                    </swiper-slide>
                    <div class="swiper-pagination" slot="pagination"></div>
                </swiper>
            </div>
        </div>
    </div>
</template>
<script>
import {mapState} from 'vuex'
export default {
    data(){
        return {
            toshow:false,   
            swiperOptions:{
                loop:true,//轮播图循环
                pagination:{//轮播图上的小圆点
                    el:".swiper-pagination"
                },
                speed:300,
                autoplay: {
                    disableOnInteraction: false, //手动滑动之后不打断播放
                    delay: 2500
                }
            }
        }
    },
    computed:{
        ...mapState(['cityName'])
    },
    methods:{
        toShow(){
            this.toshow=!this.toshow;
        },
        toCity(){
            this.$router.push({
                path:"/city"
            })
        }
    }
}
</script>
<style scoped>
    .banner-header{
        background-color:#f5f5f5;
        width:100%;
        height: 5.6rem;
        position: relative;
    }
    .banner-top{
        width:100%;
        position: absolute;
        left: 0;
        top:0.4rem;
        z-index: 2;
        height: .8rem;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .banner-left{
        position: absolute;
        left:0;
        top:0;
        background-color: #000;
        width: 6.6666rem;
        height: 100%;
        z-index: 999;

    }
    .top-left{
        padding: 0 0.4rem;

        color:#fff;
        font-size:0.426666rem;
    }
    .top-search{
        flex: 1;
        color:#333;
        border-radius: .1rem;
        background:#fff;
        font-size:.37333rem;
        padding:.2rem .2rem;
        align-items: center;
    }
    .top-right{

        padding: 0 0.3rem;
        padding-top:0.1rem;
        width: 0.8rem;
        height:0.7rem;
    }
    .top-right img{
        width: 0.53333rem;
        height:0.53333rem;
    }
    .banner-swiper{
        width:100%;
        height: 5.6rem;
    }
    .banner-swiper img{
        width: 100%;
        height: 100%;
    }
    .swiper-pagination >>>.swiper-pagination-bullet-active{
        background-color: orange;
    }
</style>