<script setup lang="ts">
	// @ts-nocheck
import { getBannerAPI } from '@/apis/home'
import { onMounted, ref } from 'vue'

const bannerList = ref([])

const getBanner = async () => {
  const res = await getBannerAPI()
  console.log(res)
  bannerList.value = res.result
}

onMounted(() => getBanner())

</script>



<template>
  <div class="home-banner">
    <!-- interval="0"代表关闭轮播，interval设置轮播间隔 -->
    <el-carousel interval="1000" height="500px">
      <el-carousel-item v-for="item in bannerList" :key="item.id">
        <img :src="item.imgUrl" alt="">
      </el-carousel-item>
    </el-carousel>
  </div>
</template>



<style scoped lang='scss'>
.home-banner {
  width: 1240px;
  height: 500px;
  position: absolute;
  left: 0;
  top: 0;
  z-index: 98;

  img {
    width: 100%;
    height: 500px;
  }
}
</style>