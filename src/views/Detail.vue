<script setup>
  import DetailTopVue from '@/components/Detail/DetailTop.vue'
  import DetailBody from '@/components/Detail/DetailBody.vue';
  import DetailNav from '@/components/Detail/DetailNav.vue';
  import { data } from '@/utils/data'
  import { useRoute } from 'vue-router'
  const route=useRoute()
  const MovieId= +route.query.id
  const DetailMovie=data.filter((item)=>item.MovieContent.id===MovieId)[0]
  // console.log(DetailMovie)

</script>

<template>
  <div :style="{backgroundColor: DetailMovie.MovieContent.themeColor}" class="Detail">
  <DetailNav></DetailNav>
  <DetailTopVue :MovieContent="DetailMovie.MovieContent"></DetailTopVue>
  <DetailBody :MovieDetail="DetailMovie"></DetailBody>
  </div>
</template>
<style lang="scss" scoped>

</style>
