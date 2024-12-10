<template>
  <view class="yl-default-header">
    <view
      :style="{ color: `${leftColor}` }"
      class="header_left"
      @click="leftClick"
    >
      {{ leftTitle }}
    </view>
    <view class="header_title">{{ title }}</view>
    <view
      :style="{ color: `${rightColor}` }"
      class="header_right"
      @click="rightClick"
    >
      {{ rightTitle }}
    </view>
  </view>
</template>
<script>
export default {
  name: "yl-default-header",
  computed: {},
  components: {},
  props: {
    // 标题
    title: {
      type: String,
      default: ""
    },
    // 左侧按钮文本
    leftTitle: {
      type: String,
      default: "取消"
    },
    // 右侧按钮文本
    rightTitle: {
      type: String,
      default: "确定"
    },
    // 左侧按钮颜色
    leftColor: {
      type: String,
      default: "#999999"
    },
    // 右侧按钮颜色
    rightColor: {
      type: String,
      default: "#ff9438"
    },
  },
  data() {
    return {};
  },
  methods: {
    leftClick() {
      this.$emit("leftClick")
    },
    rightClick() {
      this.$emit("rightClick")
    }
  }
};
</script>
<style lang="scss" scoped>
.yl-default-header {
  height: 112rpx;
  border-bottom: 1rpx solid #DDDDDD;
  display: flex;
  align-items: center;
  padding: 0 32rpx;

  .header_left {
    width: 200rpx;
    font-size: 32rpx;
  }

  .header_title {
    flex: 1;
    font-size: 36rpx;
    color: #000000;
    text-align: center;
    overflow: hidden;
    white-space: nowrap;
    text-overflow: ellipsis;
  }

  .header_right {
    width: 200rpx;
    font-size: 32rpx;
    text-align: right;
  }
}
</style>
