<template>
  <view className="home">
    <u-navbar :autoBack="true" title="卡片" />
    <view style="margin-top: 44px; padding: 24rpx; background-color: #f8f8f8">
      <yl-default-card> 有padding </yl-default-card>
      <u-divider />
      <yl-default-card :no-padding="true"> 无padding </yl-default-card>
      <u-divider />
      <view style="display: flex; align-items: center; gap: 24rpx">
        <yl-count-card title="全部" value="100" />
        <yl-count-card :selected="true" title="未开始" value="22" />
      </view>
    </view>
  </view>
</template>
<script>
import YlDefaultCard from '@/components/card/yl-default-card.vue'
import YlCountCard from '@/components/card/yl-count-card.vue'

export default {
  components: {
    YlCountCard,
    YlDefaultCard,
  },
  data() {
    return {}
  },
  methods: {},
}
</script>
<style scoped>
.home {
  height: 100vh;
  background-color: #f8f8f8;
}
</style>
