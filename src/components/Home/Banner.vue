<script setup>
    import {ref} from 'vue'
    const BannerList=ref([
    {imgUrl: "public/images/banner-img/lingdujixian.jpg", name: "零度极限", content: "体验零度极限吧！" }, 
    {imgUrl: "public/images/banner-img/tianzhuchuanqi.png", name: "天珠传奇", content: "丢失的天珠" }, 
    {imgUrl: "public/images/banner-img/xiongchumo.webp", name: "熊出没:逆转时空", content: "和光头强开启一场奇妙的时空" }, 
    {imgUrl: "public/images/banner-img/chumenzaiwai.jpg", name: "出门在外", content: "宅男成长为一个男人" }, 
    {imgUrl: "public/images/banner-img/jinshouzhi.jpg", name: "金手指", content: "加利集团主席程一言从股民偶像变成过街老鼠的故事" }, 
    {imgUrl: "public/images/banner-img/dongwuyuan.png", name: "动物园里有什么", content: "动物园里什么都有，就是没有动物！" }, 
    {imgUrl: "public/images/banner-img/nuhaiyinjiu.jpg", name: "怒海营救", content: "华裔青年们开展惊心动魄的营救人质计划" }, 
    {imgUrl: "public/images/banner-img/nuchao.jpg", name: "怒潮", content: "凶狠生猛的快节奏肉搏场面" }, 
    {imgUrl: "public/images/banner-img/huaqiangu.jpg", name: "花千骨", content: "白子画舍身甘为天下苍生，花千骨亦生死相随" }, 
    {imgUrl: "public/images/banner-img/qianxing.jpg", name: "潜行", content: "抓捕代号“老板”的幕后毒枭" }, 
    {imgUrl: "public/images/banner-img/feichengwurao.jpg", name: "非诚勿扰", content: "征婚启事 / If You Are the One III" }, 
    {imgUrl: "public/images/banner-img/relaguntang.png", name: "热辣滚烫", content: "胖女孩和帅哥的爱情故事" }
    ])
    const banner=ref()
    const BannerIndex=ref(0)
    console.log(banner)
    const BannerChange=(index)=>{
        BannerIndex.value=index
        banner.value.setActiveItem(index)
    }
</script>

<template>
    <div class="banner">
        <el-carousel ref="banner" height="40vw" direction="vertical" :autoplay="false" indicator-position="none">
            <el-carousel-item v-for="item in BannerList" :key="item">
                <template #default>
                    <div class="carousel-item">
                        <img :src="item.imgUrl" alt="">
                    </div> 
                </template>
            </el-carousel-item>
        </el-carousel>
        <div class="trigger">
            <ul>
                <li @click="BannerChange(index)" v-for="(item,index) in BannerList" :key="item" :class='{active:index===BannerIndex}'>
                    <div class="name">{{ item.name }}</div>
                    <div class="content">{{ item.content }}</div>
                </li>
            </ul>
        </div> 
    </div>
</template>

<style lang="scss" scoped>
.banner{
    display: flex;
    margin: 0 auto;
    width: 90%; 
    .el-carousel{
        margin: 0;
        width: 80%;
        height: 40vw;
        .carousel-item{
            width: 100%;
            height: 100%;
            img{
                width: 100%;
                height: 40vw;
            }
        }
    }
    .trigger{
        width: 20%;
        color: #fff;
        ul{
            height: 40vw;
            background-color: rgba($color: #fff, $alpha: .2);
            li{
                display: flex;
                align-items: center;
                flex-wrap: wrap;
                text-align: right;
                height: 3.2vw;
                width: 100%;
                padding: 0 .2rem;
                box-sizing: border-box;
                .name{
                    width: 100%;
                    font-size: 1.1rem;
                }
                .content{
                    width: 100%;
                    display: none;
                    text-align: right;
                    overflow: hidden;
                    white-space: nowrap;
                    text-overflow: ellipsis;
                }
            }
            .active{
                background-color: rgba($color: #787272, $alpha: .5);
                height: 4.8vw;
                .content{
                    display: block;
                }
            }
        }
    }
}

</style>