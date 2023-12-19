<script setup>
    const props=defineProps({
        MovieContent:Object
    })
    // console.log(props.MovieContent);
</script>
<template>
    <div class="DetailTop">
        <div class="topleft">
            <img :src="'src/'+props.MovieContent.imgUrl" alt="">
        </div>
        <div class="topright">
            <h3>{{ props.MovieContent.name }}</h3>
            <div class="type">类型: {{ props.MovieContent.type }}</div>
            <div class="director">导演: {{ props.MovieContent.director }}</div>
            <div class="star">主要演员: {{ props.MovieContent.star }}</div>
            <div class="showTime">放映时间: {{ props.MovieContent.showTime }}</div>
            <div class="company">出品公司: {{ props.MovieContent.ProCompany }}</div>
            <div class="summary">电影概述: {{ props.MovieContent.summary }}</div>
        </div>
    </div>
</template>
<style lang="scss" scoped>
.DetailTop{
    // margin-top: 2rem;
    width: 70%;
    margin: 0 auto;
    display: flex;
    .topleft{
        margin-top: 1rem;
        padding-right: 2rem;
        border-right: 3px solid plum;
        img{
            border-radius: 10px;
            width: 12.5rem;
            height: 17.5rem;
        }
    }
    .topright{
        margin-top: 1rem;
        padding-left: 1rem;
        width: 40vw;
        height: 18.5rem;
        line-height: 1.4rem;
        color: #ffffff;
        overflow: scroll;
        h3{
            font-size: 1.5rem;
            line-height: 2rem;
        }
    }
    .topright::-webkit-scrollbar{
        display: none;
    }
}
</style>