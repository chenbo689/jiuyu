<script setup>
    import { ArrowLeftBold } from '@element-plus/icons-vue'
</script>
<template>
      <el-affix>
        <template #default>
            <div class="box">
                <div class="Nav">
                    <div class="nav-left"><a href="/"><el-icon><ArrowLeftBold /></el-icon>返回</a></div>
                    <div class="nav-right">
                        <ul>
                            <li><a href="#director">导演</a></li>
                            <li><a href="#star">主要演员</a></li>
                            <li><a href="#BenchFilm">对标影视</a></li>
                            <li><a href="#ProCompany">出品公司</a></li>
                        </ul>
                    </div>
                </div>
            </div>
        </template>
      </el-affix>
      <el-backtop>

      </el-backtop>
</template>
<style lang="scss" scoped>
.el-affix{
    height: 2.5rem;
    .box{
        background-color: #fff;
    }
    .Nav{
        width: 70%;
        height: 2.5rem;
        margin: 0 auto;
        display: flex;
        justify-content: space-between;
        // align-items: center;
        font-size: 1.2rem;
        line-height: 2.5rem;
        .nav-left:hover{
            cursor: pointer;
        }
        ul{
            height: 2.5rem;
            display: flex;
            li{
                height: 2.5rem;
                box-sizing: border-box;
                padding: 0 1rem;
                a{
                    display: inline-block;
                    height: 2.5rem;
                }
            }
        }
    }
}
.el-backtop{
    bottom: 6.25rem;
    right: 6.25rem;
}

</style>