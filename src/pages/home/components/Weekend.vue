<template>
    <div>
       <div class="title">周末去哪儿</div>
       <ul>
           <li class="item border-bottom" v-for='item of recommendList' :key='item.id'>
               
               <div class="item-img-wrapper">
                   <img class="item-img" :src="item.imgUrl" >
               </div>
                   
               
               <div class="item-info">
                   <p class="item-title">{{item.title}}</p>
                   <p class="item-desc">{{item.desc}}</p>
                    
               </div>
           </li>
       </ul>
    </div>
</template>

<script>
    export default {
        name:'HomeWeekend',
        data(){
            return {
                recommendList:[{
                id:'0001',
                imgUrl:'http://img1.qunarzz.com/sight/source/1703/7a/522d4649f67319.jpg_r_640x214_2cdafd57.jpg',
                title:'九女仙湖',
                desc:'非常浪漫的地方'
            },{
                id:'0002',
                imgUrl:'http://img1.qunarzz.com/sight/source/1703/7a/522d4649f67319.jpg_r_640x214_2cdafd57.jpg',
                title:'九女仙湖',
                desc:'非常浪漫的地方'
            },{
                id:'0003',
                imgUrl:'http://img1.qunarzz.com/sight/source/1703/7a/522d4649f67319.jpg_r_640x214_2cdafd57.jpg',
                title:'九女仙湖',
                desc:'非常浪漫的地方'
            },{
                id:'0004',
                imgUrl:'http://img1.qunarzz.com/sight/source/1703/7a/522d4649f67319.jpg_r_640x214_2cdafd57.jpg',
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
    .item-img-wrapper
        overflow:hidden
        height :0    
        padding-bottom :33.9%
        .item-img
            width :100%
               
    .item-info    
         
        padding:0.1rem    
                
        .item-title
            line-height :0.54rem    
            font-size:0.32rem    
            ellipsis()    
        .item-desc    
            line-height :0.4rem    
            color :#ccc     
            ellipsis()    
         
        
</style>