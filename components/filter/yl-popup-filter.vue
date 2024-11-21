<template>
  <view class="yl-popup-filter">
    <view class="filter_btn" @tap.stop="show = true">
      <u--image :src="iconUrl || defaultIconUrl" height="14px" width="14px"/>
      <text>{{ title || '选择' }}</text>
    </view>
    <u-popup
      :customStyle="{width: `${popupWidth || 100}vw`}"
      :show="show"
      mode="right"
      @close="close"
    >
      <slot></slot>
      <view class="yl-popup-footer">
        <view class="cancel" @click="cancel">{{ cancelText || '重置' }}</view>
        <view class="confirm" @click="confirm">{{ confirmText || '确定' }}</view>
      </view>
    </u-popup>
  </view>
</template>
<script>
import {Base64} from "./../common/base64";

export default {
  name: "yl-popup-filter",
  computed: {},
  components: {},
  props: {
    title: "", // 按钮文本
    cancelText: "", // 取消按钮文本
    confirmText: "", // 确认按钮文本
    iconUrl: "", // 图标URL
    popupWidth: "", // 弹窗宽度
  },
  data() {
    return {
      defaultIconUrl: Base64.FilterImageUrl,
      show: false,
    };
  },
  methods: {
    close() {
      this.show = false;
    },
    cancel() {
      this.$emit('cancel')
    },
    confirm() {
      this.close();
      this.$emit('confirm')
    }
  }
};
</script>
<style lang="scss" scoped>
.yl-popup-filter {
  .filter_btn {
    display: flex;
    align-items: center;
    gap: 8rpx;
    padding: 16rpx 32rpx;
    height: 48rpx;
    background-color: #ffffff;
    border-radius: 24rpx;
    color: #333333;
    width: fit-content;
  }
}

.yl-popup-footer {
  display: flex;
  align-items: center;
  padding: 32rpx;

  .cancel {
    width: 240rpx;
    min-width: 100rpx;
    height: 88rpx;
    line-height: 88rpx;
    text-align: center;
    border-radius: 8rpx;
    border: 2rpx solid #dcdcdc;
    box-sizing: border-box;
  }

  .confirm {
    flex: 1;
    min-width: 100rpx;
    color: #ffffff;
    height: 88rpx;
    line-height: 88rpx;
    text-align: center;
    border-radius: 8rpx;
    background-color: #ff9438;
    border: 2rpx solid #ff9438;
    box-sizing: border-box;
    margin-left: 20rpx;
  }
}

</style>
