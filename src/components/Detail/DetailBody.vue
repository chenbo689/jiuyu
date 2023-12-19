<script setup>
import { SemiSelect } from '@element-plus/icons-vue'
const props = defineProps({
    MovieDetail: Object
})
console.log(props.MovieDetail);
const director= props.MovieDetail.directorList.director
const stars=props.MovieDetail.star
</script>
<template>
    <div class="DetailBody">
        <!-- 导演 -->
        <h2 class="title" id="director">导演</h2>
        <div class="director">
            <div class="director-top">
                <div class="director-left">
                    <span class="name">{{ director.name }}</span>
                    <span class="identity">{{ director.identity }}</span>
                    <div class="backgroud" v-for="item in director.background" :key="item">{{ item }}</div>
                    <h3>历史成就</h3>
                    <div class="achieve" v-for="item in director.achieve" :key="item">{{ item }}</div>
                </div>
                <div class="director-right">
                    <img :src="'src/' + director.photo" alt="">
                </div>
            </div>
            <div class="director-bottom">
                <img :src="'src/' + director.repreWork" alt="">
            </div>
        </div>
        <!-- 主要演员 -->
        <h2 class="title" id="star">主要演员</h2>
        <div class="star">
            <div class="director" v-for="item in stars" :key="item">
                <div class="director-top">
                    <div class="director-left">
                        <span class="name">{{ item.name }}</span>
                        <div class="backgroud" v-for="item1 in item.background" :key="item1">{{ item1 }}</div>
                        <h3>人物简历</h3>
                        <div class="Charresume">{{ item.Charresume }}</div>
                    </div>
                    <div class="director-right">
                        <img :src="'src/' + item.photo" alt="">
                    </div>
                </div>
                <div class="director-bottom">
                    <img :src="'src/' + item.repreWork" alt="">
                </div>
            </div>
        </div>
        <!-- 对标影视 -->
        <h2 class="title" id="BenchFilm">对标影视</h2>
        <div class="BenchFilm">
            <div class="Film" v-for="item in MovieDetail.BenchFilm" :key="item">
                <div class="FilmTop">
                    <div class="FilmTop-left">
                        <h3>{{ item.name }}</h3>
                        <div class="FilmContent">
                            <div class="type">类型:{{ item.type }}</div>
                            <div class="director">导演:{{ item.director }}</div>
                            <div class="stars">主演:{{ item.star }}</div>
                            <div class="booking">票房:{{ item.booking }}</div>
                            电影概述: <div class="describe">{{ item.describe }}</div>
                        </div>
                    </div>
                    <div class="FilmTop-right">
                        <img :src="'src/' + item.imgUrl" alt="">
                    </div> 
                </div>
                <ul class="FilmAward">
                    <li v-for="item1 in item.Award" :key="item1">
                        <span class="time">{{ item1.time }}</span>
                        <el-icon><SemiSelect /></el-icon>
                        <span class="award">{{ item1.award }}</span>
                    </li>
                </ul>
            </div>
        </div>
        <!-- 出品公司 -->
        <h2 class="title" id="ProCompany">出品公司</h2>
        <div class="ProCompany">
            <div class="Company" v-for="item in MovieDetail.ProCompany" :key="item">
                <h3>{{ item.name }}</h3>
                <img :src="'src/'+item.imgUrl" alt="">
                <div class="CompanyContent">{{ item.content }}</div>
                <img :src="'src/'+item.repreWork" alt="">
            </div>
        </div>
    </div>
</template>
<style lang="scss" scoped>
    .DetailBody{
        width: 70%;
        margin: 1rem auto;
        padding: 1rem;
        box-sizing: border-box;
        background-color: #ECEEEF;
        .title{
            line-height: 2rem;
            font-size: 1.6rem;
            padding-left: .4rem;
            border-left: .4rem solid skyblue;
            margin: .2rem 0;
        }
        .director{
            width: 100%;
            .director-top{
            margin-top: 2rem;
            display: flex;
            justify-content: space-evenly;
            .director-left{
                height: 17.5rem;
                overflow: scroll;
                overflow-x: hidden;
                width: 40%;
                .name{
                    font-size: 1.4rem;
                    font-weight: 600;
                    line-height: 1.6rem;
                    border-bottom: 2px solid pink;
                }
                .identity{
                    margin-left: .3rem;
                    line-height: 1.6rem;
                    font-weight: 600;
                }
                .backgroud{
                    line-height: 1.3rem;
                }
                h3{
                    font-size: 1.4rem;
                    line-height: 1.6rem;
                }
                line-height: 1.4rem;
            }
            .director-left::-webkit-scrollbar{
                    display: none;
                }
            .director-right{
                img{
                    width: 12.5rem;
                    height: 17.5rem;
                    border-radius: 10px;
                }
            }
            }
            .director-bottom{
                margin-top: 1rem;
                text-align: center;
                img{
                    width: 75%;
                }
            }
        }
        .star{
            display: flex;
            overflow: scroll;
            overflow-y: hidden;
            .director{
                width: 80%;
                flex-shrink: 0;
            }
        }  
        .BenchFilm{
            .Film{
                width: 80%;
                margin: 2rem auto;
                .FilmTop{
                    display: flex;
                    .FilmTop-left{
                        margin-right: 2rem;
                        width: 55%;
                        height: 19rem;
                        flex-shrink: 0;
                        line-height: 1.2rem;
                        align-items: center;
                        h3{
                            font-size: 1.4rem;
                            line-height: 2rem;
                        }
                        .describe{
                            height: 9.4rem;
                            overflow: scroll;
                            overflow-x: hidden;
                            text-indent: 2rem;
                        }
                         .describe::-webkit-scrollbar{
                            display: none;
                         }
                        
                    }
                    img{
                        width: 10rem;
                        // height: 17.5rem;
                    }
                }
                .FilmAward{
                    li{
                        height: 2rem;
                        line-height: 2rem;
                        font-size: 1.2rem;
                        position: relative;
                        .time{
                            display: inline-block;
                            width: 10rem;
                        }
                        .award{
                            margin-left: .8rem;
                        }
                    }
                }
            }
        }
        .ProCompany{
            width: 80%;
            margin: 1rem auto;
            .Company{
                text-align: center;
                h3{
                    text-align: left;
                    font-size: 1.4rem;
                    line-height: 1.8rem;
                }
                img{
                    margin: .6rem 0;
                    width: 80%;
                }
                .CompanyContent{
                    text-align: left;
                    text-indent: 2rem;
                }
            }
        }
    }
</style>