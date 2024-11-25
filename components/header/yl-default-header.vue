<template>
  <view class="yl-default-header">
    <view class="header_left" @click="leftClick">{{ leftTitle }}</view>
    <view class="header_title">{{ title }}</view>
    <view class="header_right" @click="rightClick">{{ rightTitle }}</view>
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
  background-color: #F9F9F9;
  height: 112rpx;
  border-bottom: 1rpx solid #DDDDDD;
  display: flex;
  align-items: center;
  padding: 0 32rpx;

  .header_left {
    width: 200rpx;
    font-size: 32rpx;
    color: #999999;
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
    color: #14191E;
    text-align: right;
  }
}
</style>
