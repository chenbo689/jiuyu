<script setup>
    // import {ref} from 'vue'
    import {data} from '@/utils/data.js'
    console.log(data);
    const MovieContent=data.map(item=>item.MovieContent)
    console.log(MovieContent);
</script>
<template>
    <div class="MainMovie">
        <ul>
            <li v-for="(item) in MovieContent" :key="item">
                <router-link :to="'/detail?id='+item.id">
                    <img :src="'src/' + item.imgUrl" alt="">
                    <div class="ContentBottom">
                        <div class="name">{{ item.name }}</div>
                        <div class="type">{{ item.type }}</div>
                        <div class="content">{{ item.content }}</div>
                    </div>
                </router-link>
            </li>
        </ul>
    </div>
</template>
<style lang="scss" scoped>
.MainMovie{
    margin: 0 auto;
    width: 90%; 
    margin-top: 20px;
    ul{
        display: flex;
        flex-wrap: wrap;
        justify-content: space-around;
        li{
            margin-top: .2rem;
            flex-shrink: 2;
            width: 12.5rem;
            height: 22.4rem;
            margin: 0 .2rem;
            color: #fff;
            img{
                width: 12.5rem;
                height: 17.5rem;
                border-radius: 5px;
            }
            .ContentBottom{
                box-sizing: border-box;
                padding-left: .2rem;
                .name{
                    font-size: 1.2rem;
                    line-height: 1.4rem;
                }
                .type{
                    font-size: .8rem;
                    line-height: 1rem;
                }
                .content{
                    font-size: .8rem;
                    line-height: 1rem;
                    display: none;
                }
            }
        }
        li:hover{
            border-radius: 10px;
            background-color: rgba($color: #3f3f3f, $alpha: 1.0);
            .content{
                display: block;
            }
        }
    }
}
</style>