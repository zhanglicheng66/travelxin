<template>
    <ul class="list">
        <li class="item" v-for="item in letters" 
        :key="item" 
        @click="handleLetterClick" 
        :ref="item"
        @touchstart="handleTouchStart"
        @touchmove="handleTouchMove"
        @touchend="handleTouchEnd"
        >
            {{item}}
        </li>
        
    </ul>
</template>

<script>
    export default {

        props:{
            cities:Object
        },
        computed:{
            letters(){
                const letters=[]
                for(let i in this.cities){
                    letters.push(i)
                }
                console.log(letters)
                return letters
            }
        },
        updated(){
            this.startY=this.$refs['A'][0].offsetTop
        },
        data(){
            return{
                touchStatus:false,
                startY:0,
                timer:null
            }
        },
        methods:{
            handleLetterClick(e){
                this.$emit('change',e.target.innerText)
                console.log(e.target.innerText)
            },
            handleTouchStart(){
                this.touchStatus=true
                console.log('开始触摸')
            },
            handleTouchMove(e){
                if(this.touchStatus){
                    if(this.timer){
                        clearTimeout(this.timer)
                    }
                    this.timer=setTimeout(()=>{
                        // const startY= this.$refs['A'][0].offsetTop
                        const touchY = e.touches[0].clientY-79
                        const index = Math.floor((touchY-this.startY)/20)
                        console.log(index)
                        if(index >= 0 && index <this.letters.length){
                            this.$emit('change',this.letters[index])
                        }
                    },15)

                    
                    
                }
            },
            handleTouchEnd(){
                this.touchStatus = false
            }
        }
        
    }
</script>

<style lang='stylus' scoped>
    @import '~styles/varibles.styl'
    .list
        display :flex
        flex-direction:column
        justify-content :center
        position :absolute
        top:1.58rem 
        right:0
        bottom:0
        width:0.4rem
        // background:red
        .item
            line-height:0.4rem
            text-align :center
            color:$bgColor

</style>