<template>
  <view className="home">
    <u-navbar :autoBack="true" title="卡片"/>
    <view style="margin-top: 44px;padding: 24rpx;background-color: #f8f8f8;">
      <yl-default-card>
        <view style="display: flex;align-items: center;gap: 20rpx;">
          <yl-ellipsis :suffix-count="6" color="#999" size="30rpx"
                       text="我是标题我是标题我是标题我是标题我是标题我是标题我是标题.pdf"/>
          <view style="color: red;white-space: nowrap;">删除</view>
        </view>
      </yl-default-card>
      <u-divider/>
    </view>
  </view>
</template>
<script>
import YlDefaultCard from "@/components/card/yl-default-card.vue";
import YlEllipsis from "@/components/ellipsis/yl-ellipsis.vue";

export default {
  components: {
    YlEllipsis,
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
