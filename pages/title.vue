<template>
  <view className="home">
    <u-navbar :autoBack="true" title="标题" />
    <view style="margin-top: 44px; padding: 24rpx; background-color: #f8f8f8">
      <yl-default-card>
        <yl-default-title
          title="标题标题标题标题标题标题标题标题标题标题标题标题"
        >
          <template #extend>
            <view
              style="display: flex; align-items: center; margin-left: 20rpx"
            >
              <yl-default-tag />
              <yl-default-tag />
              <yl-default-tag />
            </view>
          </template>
          <template #content>
            <view
              style="display: flex; align-items: center; margin-left: 20rpx"
            >
              <text style="white-space: nowrap">进行中</text>
              <u-icon color="#999999" name="arrow-right" size="14" />
            </view>
          </template>
        </yl-default-title>
        <u-divider />
        <yl-default-title title="任务信息" title-height="80rpx">
          <template #content>
            <text style="color: #9194a5; font-size: 28rpx">未开始</text>
          </template>
        </yl-default-title>
        <u-divider />
        <yl-default-title title="任务信息" title-height="80rpx">
          <template #content>
            <view style="display: flex; align-items: center">
              <text style="white-space: nowrap; color: #ff9438">查看详情</text>
              <u-icon color="#999999" name="arrow-right" size="14" />
            </view>
          </template>
        </yl-default-title>
        <u-divider />
        <yl-form-title :required="true" title="测试标题">
          <template #content>
            <view style="display: flex; align-items: center">
              <text style="white-space: nowrap; color: #ff9438">查看详情</text>
              <u-icon color="#999999" name="arrow-right" size="14" />
            </view>
          </template>
        </yl-form-title>
      </yl-default-card>
    </view>
  </view>
</template>
<script>
import YlDefaultCard from '@/components/card/yl-default-card.vue'
import YlCountCard from '@/components/card/yl-count-card.vue'
import YlDefaultTitle from '@/components/title/yl-default-title.vue'
import YlDefaultTag from '@/components/tag/yl-default-tag.vue'
import YlFormTitle from '@/components/title/yl-form-title.vue'

export default {
  components: {
    YlFormTitle,
    YlDefaultTag,
    YlDefaultTitle,
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
