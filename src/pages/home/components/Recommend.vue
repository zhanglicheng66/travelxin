<template>
    <div>
       <div class="title">热销推荐</div>
       <ul>
           <li class="item border-bottom" v-for='item of list' :key='item.id'>
               
                   <img class="item-img" :src="item.imgUrl" >
               
               <div class="item-info">
                   <p class="item-title">{{item.title}}</p>
                   <p class="item-desc">{{item.desc}}</p>
                   <button class="item-button">查看详情</button>
               </div>
           </li>
       </ul>
    </div>
</template>

<script>
    export default {
        name:'HomeRecommend',
        props:{
            list:Array
        },
        data(){
            return {
                recommendList:[{
                id:'0001',
                imgUrl:'http://img1.qunarzz.com/sight/p0/201301/10/18cb7bc9c1fd853193835fbb.png_200x200_06614dcb.png',
                title:'九女仙湖',
                desc:'非常浪漫的地方'
            },{
                id:'0002',
                imgUrl:'http://img1.qunarzz.com/sight/p0/201301/10/18cb7bc9c1fd853193835fbb.png_200x200_06614dcb.png',
                title:'九女仙湖',
                desc:'非常浪漫的地方'
            },{
                id:'0003',
                imgUrl:'http://img1.qunarzz.com/sight/p0/201301/10/18cb7bc9c1fd853193835fbb.png_200x200_06614dcb.png',
                title:'九女仙湖',
                desc:'非常浪漫的地方'
            },{
                id:'0004',
                imgUrl:'http://img1.qunarzz.com/sight/p0/201301/10/18cb7bc9c1fd853193835fbb.png_200x200_06614dcb.png',
                title:'九女仙湖',
                desc:'非常浪漫的地方'
            },]
            }
        }
    }
</script>

<style lang='stylus' scoped>
    @import '~styles/mixins.styl'
    .title
        margin-top :0.2rem
        line-height:0.8rem
        background:#eee
        text-indent:0.2rem
    .item
        overflow :hidden
        display :flex 
        height :1.9rem
        
        .item-img
            width :1.7rem
            height :1.7rem
            padding : 0.1rem
        .item-info
            flex :1
            padding:0.1rem
            min-width:0
            .item-title
                line-height :0.54rem
                font-size:0.32rem
                ellipsis()
            .item-desc
                line-height :0.4rem
                color :#ccc 
                ellipsis()
            .item-button
                line-height :0.44rem
                margin-top:0.16rem
                background #ff9300
                padding:0 0.2rem
                border-radius:0.06rem    
                color:#fff
</style>