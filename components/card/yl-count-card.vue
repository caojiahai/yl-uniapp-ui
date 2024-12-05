<template>
  <view :style="{ background: selected ? '#ffffff' : 'unset' }" class="yl-count-card">
    <view :style="{ color: selected ? selectColor : valueColor }" class="count-value">{{ value }}</view>
    <view :style="{ color: selected ? selectColor : titleColor }" class="count-title">{{ title }}</view>
  </view>
</template>
<script>
export default {
  name: "yl-count-card",
  computed: {},
  components: {},
  props: {
    // 标题
    title: {
      type: String,
      default: ""
    },
    // 标题
    value: {
      type: Number,
      default: 0
    },
    // 颜色
    valueColor: {
      type: String,
      default: '#634D3E'
    },
    // 颜色
    titleColor: {
      type: String,
      default: '#AB8864'
    },
    // 选中颜色
    selectColor: {
      type: String,
      default: '#FF9438'
    },
    // 选中
    selected: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {};
  },
  methods: {}
};
</script>
<style lang="scss" scoped>
.yl-count-card {
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 152rpx;
  min-width: 152rpx;
  height: 108rpx;
  border: 1rpx solid #FFFFFF;
  border-radius: 16rpx;

  .count-value {
    font-size: 32rpx;
    font-weight: 500;
    line-height: 48rpx;
    text-align: center;
  }

  .count-title {
    font-size: 24rpx;
    line-height: 32rpx;
    text-align: center;
  }
}
</style>
