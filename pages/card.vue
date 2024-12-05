<template>
  <view className="home">
    <u-navbar :autoBack="true" title="卡片"/>
    <view style="margin-top: 44px;padding: 24rpx;background-color: #f8f8f8;">
      <yl-default-card>
        有padding
      </yl-default-card>
      <u-divider/>
      <yl-default-card :no-padding="true">
        无padding
      </yl-default-card>
    </view>
  </view>
</template>
<script>
import YlDefaultCard from "@/components/card/yl-default-card.vue";

export default {
  components: {
    YlDefaultCard
  },
  data() {
    return {}
  },
  methods: {}
}
</script>
<style scoped>
.home {
  height: 100vh;
  background-color: #f8f8f8;
}
</style>
