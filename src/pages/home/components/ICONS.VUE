<template>
    <div class="icons">
        <swiper>
            <swiper-slide v-for='(page,index) in pages' :key='index'>
                <div class="icon" v-for='item in page' :key='item.id'>
                    <div class="icon-img">
                        <img class="icon-img-content" :src="item.imgUrl" alt="">
                    </div>
                    
                    <p class="icon-desc">{{item.desc}}</p>
                </div>
            </swiper-slide>
        </swiper>
        
    </div>
</template>

<script>
    name:'HomeIcons'
    export default {
        data(){
            return{
                iconList:[{
                    id:'0001',
                    imgUrl:'https://gw.alicdn.com/tfs/TB1Wxi2trsrBKNjSZFpXXcXhFXa-183-144.png',
                    desc:'景点门票'
                },{
                    id:'0002',
                    imgUrl:'https://gw.alicdn.com/tfs/TB1Wxi2trsrBKNjSZFpXXcXhFXa-183-144.png',
                    desc:'滑雪季节'
                },{
                    id:'0003',
                    imgUrl:'https://gw.alicdn.com/tfs/TB1Wxi2trsrBKNjSZFpXXcXhFXa-183-144.png',
                    desc:'泡温泉'
                },{
                    id:'0004',
                    imgUrl:'https://gw.alicdn.com/tfs/TB1Wxi2trsrBKNjSZFpXXcXhFXa-183-144.png',
                    desc:'动植园'
                },{
                    id:'0005',
                    imgUrl:'https://gw.alicdn.com/tfs/TB1Wxi2trsrBKNjSZFpXXcXhFXa-183-144.png',
                    desc:'滑雪季节'
                },{
                    id:'0006',
                    imgUrl:'https://gw.alicdn.com/tfs/TB1Wxi2trsrBKNjSZFpXXcXhFXa-183-144.png',
                    desc:'滑雪季节'
                },{
                    id:'0007',
                    imgUrl:'https://gw.alicdn.com/tfs/TB1Wxi2trsrBKNjSZFpXXcXhFXa-183-144.png',
                    desc:'滑雪季节'
                },{
                    id:'0008',
                    imgUrl:'https://gw.alicdn.com/tfs/TB1Wxi2trsrBKNjSZFpXXcXhFXa-183-144.png',
                    desc:'滑雪季节'
                },{
                    id:'0009',
                    imgUrl:'https://gw.alicdn.com/tfs/TB1Wxi2trsrBKNjSZFpXXcXhFXa-183-144.png',
                    desc:'一日游'
                }]
            }
        },
        computed: {
            pages (){
                const pages = []
                this.iconList.forEach((item,index)=>{
                    const page = Math.floor(index/8)
                    if(!pages[page]){
                        pages[page]=[]
                    }
                    pages[page].push(item)
                })
                return pages
            }
        },
    }
</script>

<style  lang='stylus' scoped>
        .icons >>> .swiper-container
            height :0
            padding-bottom:50%
        .icon
            position:relative
            overflow: hidden
            float: left
            width :25%
            height :0
            padding-bottom:25%
            // background :red
            .icon-img
                position :absolute
                top:0
                left:0
                right :0
                bottom:0.44rem
                box-sizing:border-box
                padding:0.1rem
                // background:blue 
                .icon-img-content
                    display:block
                    margin :0 auto
                    height :100%
            .icon-desc 
                position :absolute
                left:0
                right:0
                bottom:0
                height :0.44rem
                line-height:0.44rem
                text-align :center
                color:#333
                overflow :hidden
                white-space :nowrap
                text-overflow: ellipsis
                



</style>