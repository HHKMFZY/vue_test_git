<script setup lang="ts">

import LayoutNav from './components/LayoutNav.vue'
import LayoutHeader from './components/LayoutHeader.vue'
import LayoutFooter from './components/LayoutFooter.vue'

</script>

<template>
  <LayoutNav />
  <LayoutHeader />
  <LayoutFooter />
我是首页
<!-- 二级路由出口 -->
<RouterView></RouterView>
</template>