<template>
  <view :style="{ border: `1rpx solid ${color}` }" class="yl-tab-tag">
    <view
      v-if="title"
      :style="{ backgroundColor: `${color}` }"
      class="tab-title"
      >{{ title }}</view
    >
    <view
      v-if="subTitle"
      :style="{ color: `${color}` }"
      class="tab-sub-title"
      >{{ subTitle }}</view
    >
  </view>
</template>
<script>
export default {
  name: 'yl-tab-tag',
  computed: {},
  components: {},
  props: {
    // 标题
    title: {
      type: String,
      default: '',
    },
    // 副标题
    subTitle: {
      type: String,
      default: '',
    },
    // 颜色
    color: {
      type: String,
      default: '#ff9438',
    },
  },
  data() {
    return {}
  },
  methods: {},
}
</script>
<style lang="scss" scoped>
.yl-tab-tag {
  border-radius: 6rpx;
  display: flex;
  align-items: center;
  width: fit-content;
  box-sizing: border-box;

  .tab-title {
    color: #ffffff;
    font-size: 20rpx;
    font-weight: 400;
    height: 26rpx;
    line-height: 26rpx;
    background-color: #ff9438;
    padding: 4rpx;
  }

  .tab-sub-title {
    background-color: #ffffff;
    font-size: 20rpx;
    font-weight: 400;
    height: 26rpx;
    line-height: 26rpx;
    color: #ff9438;
    padding: 0 4rpx;
  }
}
</style>
