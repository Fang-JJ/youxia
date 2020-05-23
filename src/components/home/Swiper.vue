<template>
    <div class="ad-swiper">
        <swiper :options="swiperOptions">
            <swiper-slide>
                <img src="@/assets/img/swiper1.png" alt="">
            </swiper-slide>
            <swiper-slide>
                <img src="@/assets/img/swiper2.png" alt="">
            </swiper-slide>
            <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
    </div>
</template>

<script>
export default {
    data(){
        return{
            swiperOptions:{
                loop:true,//轮播图循环
                pagination:{//轮播图上的小圆点
                    el:".swiper-pagination"
                },
                speed:300,
                autoplay:{
                    disableOnInteraction: false, //手动滑动之后不打断播放
                    delay: 3000
                }
            }
        }
        
    }
}
</script>

<style scoped>
    .ad-swiper{
        background: #fff9db;
        width:100%;
        height: 3.2rem;
    }
    .ad-swiper img{
        width:100%;
        height: 3.2rem;
    }
    .swiper-pagination-bullets >>> .swiper-pagination-bullet-active{
        background-color: orange;
    }
</style>