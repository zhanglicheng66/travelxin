<template>
    <div class="search">
        <input class="search-input" type="text" placeholder="输入城市名或拼音">
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="stylus" scoped>
    @import '~styles/varibles.styl'
    .search
        
        height 0.62rem
        padding:0.1rem
        margin-top :-0.1rem
        background :$bgColor  
        .search-input
            box-sizing :border-box
            width:100% 
            height :0.62rem
            padding:0 0.2rem
            line-height :0.62rem
            border-radius :0.06rem 
            color:#666   
</style>