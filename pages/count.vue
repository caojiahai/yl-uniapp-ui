<template>
  <view className="home">
    <u-navbar :autoBack="true" title="倒计时" />
    <view style="margin-top: 44px; padding: 24rpx; background-color: #f8f8f8">
      <yl-default-card>
        <yl-count-down end-time="2024-12-08" />
        <u-divider />
        <yl-count-down end-time="2024-12-09" />
      </yl-default-card>
    </view>
  </view>
</template>
<script>
import YlDefaultCard from '@/components/card/yl-default-card.vue'
import YlCountDown from '@/components/count/yl-count-down.vue'

export default {
  components: {
    YlCountDown,
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
