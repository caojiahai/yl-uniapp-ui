<template>
  <view class="yl-item-layout-list">
    <view class="item-label">{{ label }}</view>
    <template>
      <slot name="content"></slot>
    </template>
  </view>
</template>
<script>
export default {
  name: 'yl-item-layout-list',
  computed: {},
  components: {},
  props: {
    // 标签名称
    label: {
      type: String,
      default: '',
    },
  },
  data() {
    return {}
  },
  methods: {},
}
</script>
<style lang="scss" scoped>
.yl-item-layout-list {
  padding: 16rpx 0;

  .item-label {
    color: #666666;
    font-size: 28rpx;
    line-height: 40rpx;
  }
}
</style>
