<template>
    <div class="list">
        <div class="city-item">
            <p>定位/附近的站点</p>
            <div v-for="item in mapCities " :key='item.id' @click="toHome(item.name)">{{item.name}}</div>
        </div>
        <div class="city-item">
            <p>已开通周边旅游站点</p>
            <div v-for="item in cities " :key='item.id' @click="toHome(item.name)">{{item.name}}</div>
        </div>
        <div class="city-item">
            <p>热门玩乐城市</p>
            <div v-for="item in hotCities " :key='item.id' @click="toHome(item.name)">{{item.name}}</div>
        </div>
    </div>
</template>

<script>
import {mapMutations} from 'vuex'
export default {
    data(){
        return{
            mapCities:[],
            cities:[],
            hotCities:[]
        }
        
    },
    methods:{
        toHome(city){
            this.changeCity(city),
            this.$router.push({
                path:"/"
            })
        },
        ...mapMutations(['changeCity'])
    },
    
    mounted(){
        let That =this;
        this.axios.get("http://localhost:8080/api/city.json").then((res)=>{
            let data = res.data.data;
            That.mapCities=data.mapCities;
            That.cities=data.cities;
            That.hotCities=data.hotCities;
        })
    }
}
</script>

<style scoped>
.city-item{
    padding-left: .4rem;
    color:#999;
    font-size: .35rem;
}
.city-item p{
    padding: .3rem 0;
}
.city-item div{
    display: inline-block;
    width: 2rem;
    height: .82rem;
    text-align: center;
    line-height: .82rem;
    border: 1px solid #ccc;
    border-radius: .2rem;
    margin-right: .4rem;
    margin-top: .2rem;
    box-sizing: border-box;

}
</style>