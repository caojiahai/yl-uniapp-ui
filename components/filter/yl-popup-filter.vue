<template>
  <view class="yl-popup-filter">
    <view class="filter_btn" @tap.stop="show = true">
      <u--image :src="iconUrl || defaultIconUrl" height="14px" width="14px"/>
      <text>{{ title || '选择' }}</text>
    </view>
    <u-popup
      :customStyle="{width: '100vw'}"
      :show="show"
      mode="right"
      @close="close"
    >
      <u-navbar :autoBack="false" :title="popupTitle || '标题'" @leftClick="close"/>
      <view class="yl-popup-body">
        <slot></slot>
      </view>
      <view class="yl-popup-footer">
        <view @click="cancel">{{ cancelText || '重置' }}</view>
        <view @click="confirm">{{ confirmText || '确定' }}</view>
      </view>
    </u-popup>
  </view>
</template>
<script>
import {Base64} from "@/components/common/base64";

export default {
  name: "yl-popup-filter",
  computed: {},
  components: {},
  props: {
    title: "", // 按钮文本
    popupTitle: "", // 弹窗标题
    cancelText: "", // 取消按钮文本
    confirmText: "", // 确认按钮文本
    iconUrl: "", // 图标URL
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

.yl-popup-body {
  margin-top: 44px;
}

</style>
