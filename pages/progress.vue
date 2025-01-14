<template>
  <view className="home">
    <u-navbar :autoBack="true" title="进度条" />
    <view style="margin-top: 44px; padding: 24rpx; background-color: #f8f8f8">
      <yl-default-card>
        <yl-default-progress :percentage="50" />
        <u-divider />
        <yl-default-progress
          :percentage="50"
          :percentage-text="'1/2'"
          color="#ff5925"
          lg-form-color="#ffad3a"
          lg-to-color="#ff6320"
        />
      </yl-default-card>
    </view>
  </view>
</template>
<script>
import YlDefaultCard from '@/components/card/yl-default-card.vue'
import YlDefaultProgress from '@/components/progress/yl-default-progress.vue'

export default {
  components: {
    YlDefaultProgress,
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
