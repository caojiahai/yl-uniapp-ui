<template>
  <view class="home">
    <u-navbar
      :autoBack="false"
      leftIcon=""
      title="首页"
    />
    <view style="margin-top: 44px;padding: 24rpx;">
      <yl-default-card>
        <yl-default-list title="标签" @listClick="goNext('/pages/tag')"/>
        <yl-default-list title="进度" @listClick="goNext('/pages/progress')"/>
        <yl-default-list title="列表" @listClick="goNext('/pages/list')"/>
        <yl-default-list title="头部" @listClick="goNext('/pages/header')"/>
        <yl-default-list title="表单" @listClick="goNext('/pages/form-item')"/>
        <yl-default-list title="过滤" @listClick="goNext('/pages/filter')"/>
        <yl-default-list title="日期" @listClick="goNext('/pages/date')"/>
        <yl-default-list title="倒计时" @listClick="goNext('/pages/count')"/>
        <yl-default-list title="卡片" @listClick="goNext('/pages/card')"/>
        <yl-default-list title="标题" @listClick="goNext('/pages/title')"/>
      </yl-default-card>
    </view>
  </view>
</template>
<script>
import YlDefaultCard from "@/components/card/yl-default-card.vue";
import YlDefaultList from "@/components/list/yl-default-list.vue";

export default {
  components: {
    YlDefaultList,
    YlDefaultCard
  },
  data() {
    return {}
  },
  methods: {
    goNext(val) {
      uni.navigateTo({
        url: val
      })
    },
  }
}
</script>
<style>
.home {
  height: 100vh;
  background-color: #f8f8f8;
}
</style>
