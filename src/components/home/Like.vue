<template>
    <div class="like">
        <div class="like-list" v-for="(item,index) in likeList" :key="index">
            <div class="like-top">
                <div class="top-left">
                    <span>{{item.title}}</span>
                </div>
                <p class="top-right">更多</p>
            </div>
            <div class="like-bottom">
                <div class="bottom-header"
                    :style="{'background':'url('+item.imgUrl+')'}"
                >
                    <div class="header-info">
                        <span>
                            {{item.Introduction}}
                        </span>
                        <span>${{item.price}}起</span>
                    </div>
                </div>
                <ul>
                    <li v-for="n in item.cityList" :key="n">
                        <img :src="n.imgUrl" alt="">
                        <span class="title">{{n.title}}</span>
                        <span class="price">￥{{n.price}}起</span>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props:['likeList']
}
</script>

<style scoped>
    .like{
        margin-top: .7rem;
        font-size: .35rem;
        padding-bottom: 1.2rem;

    }
    .like-top{
        display: flex;
        justify-content: space-between;
    }
    .like-top .top-left{
        position: relative;
    }
    .like-top .top-left span{
        padding-left: .5rem;
        font-size: .5rem;
    }
    .like-top .top-left:before{
        position: absolute;
        content: "";
        background: #fed101;
        width: .1rem;
        height: .6666666rem;
    }
    .like-top .top-right{
        padding-right: .5rem;
        color:#999;
        font-weight: 600;
        font-size: .45rem;
    }
    .like-bottom{
        padding:.3rem;
    }
    .like-bottom .bottom-header{
        position: relative;
        height: 4.46666rem;
        width:100%;
        background-size:100%;
    }
    .like-bottom .bottom-header .header-info{
        width:96%;
        position: absolute;
        bottom:.26rem ;
        left: .2rem;
        display: flex;
        
    }
    .like-bottom .bottom-header .header-info span:nth-child(1){
        font-size: .5rem;
        width:5.78rem;
        flex: 1;
        color:#fff;
        font-weight: 700;
        white-space: nowrap;
        text-overflow: ellipsis;
        overflow: hidden;
    }
    .like-bottom .bottom-header .header-info span:nth-child(2){
        font-size: .45rem;
        color:orange;
        font-weight: 700;
        margin-left: 1rem;
    }
    .like-bottom ul{
        display: flex;
        justify-content: center;
        margin-top: .3rem;
    }
    .like-bottom ul li{
        display: block;
        margin-right: .2rem;
        border:1px soild #fff;
        border-radius: .3rem;
    }
    .like-bottom ul li img{
        width: 100%;
        height:1.9584rem;
    }
    .like-bottom ul li span.title{
        font-size: .35rem;
        display: block;
        margin-top: .2rem;
        height: 0.69333rem;
        width: 100%;
        display: block;
        /* -webkit-box-orient: vertical;
        -webkit-line-clamp: 2;
        overflow: hidden; */
        text-overflow: ellipsis;

    }
    .like-bottom ul li span.price{
        display: block;
        margin-top: .35rem;
        color:orange;
        font-weight: 500;
        font-size: .35rem;
    }
</style>