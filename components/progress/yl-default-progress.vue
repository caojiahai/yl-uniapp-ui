<template>
  <view
    :style="{
      backgroundColor: `${bgColor}`,
    }"
    class="yl-default-progress"
  >
    <view
      :style="{
        width: `${percentage}%`,
        background: `linear-gradient(to ${lgDirection}, ${lgFormColor}, ${lgToColor})`,
      }"
      class="progress-value"
    >
      <view
        :style="{
          right: getPercentageStyle(),
          backgroundColor: `${color}`,
        }"
        class="progress-percentage"
      >
        {{ percentageText ? percentageText : `${percentage}%` }}
      </view>
    </view>
    <view
      :style="{
        border: `3rpx solid ${color}`,
      }"
      class="progress-end"
    />
  </view>
</template>
<script>
export default {
  name: 'yl-default-progress',
  props: {
    // 进度
    percentage: {
      type: Number,
      default: 0,
    },
    // 进度
    percentageText: {
      type: String,
      default: '',
    },
    // 默认颜色
    color: {
      type: String,
      default: '#40C381',
    },
    // 默认进度条背景色
    bgColor: {
      type: String,
      default: '#EDEDED',
    },
    // 渐变开始颜色
    lgFormColor: {
      type: String,
      default: '#60BF0E',
    },
    // 渐变结束颜色
    lgToColor: {
      type: String,
      default: '#18BD6A',
    },
    // 渐变方向
    lgDirection: {
      type: String,
      default: 'right',
    },
  },
  data() {
    return {}
  },
  methods: {
    getPercentageStyle() {
      // 防止进度块溢出
      if (this.percentage < 25) {
        return '-70rpx'
      } else if (this.percentage > 75) {
        return '0rpx'
      } else {
        return '-35rpx'
      }
    },
  },
}
</script>
<style lang="scss" scoped>
.yl-default-progress {
  display: flex;
  align-items: center;
  height: 16rpx;
  border-radius: 10rpx;
  position: relative;

  .progress-value {
    height: 16rpx;
    border-radius: 20rpx;
    position: relative;

    .progress-percentage {
      position: absolute;
      right: -35rpx;
      top: -8rpx;
      width: 70rpx;
      height: 32rpx;
      border-radius: 30rpx;
      border: 2rpx solid #ffffff;
      text-align: center;
      line-height: 32rpx;
      font-size: 24rpx;
      font-weight: 500;
      color: #ffffff;
      box-sizing: border-box;
      z-index: 1;
    }
  }

  .progress-end {
    position: absolute;
    right: 0;
    top: 0;
    width: 16rpx;
    height: 16rpx;
    border-radius: 50%;
  }
}
</style>
