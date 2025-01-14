<template>
  <view class="yl-popup-filter">
    <template>
      <slot name="content"></slot>
    </template>
    <u-popup
      :customStyle="{ width: `${popupWidth}vw` }"
      :show="show"
      mode="right"
      @close="close"
    >
      <template>
        <slot name="popup"></slot>
      </template>
    </u-popup>
  </view>
</template>
<script>
export default {
  name: 'yl-popup-filter',
  computed: {},
  components: {},
  props: {
    // 是否显示
    show: {
      type: Boolean,
      default: false,
    },
    // 弹窗宽度
    popupWidth: {
      type: Number,
      default: 100,
    },
  },
  data() {
    return {}
  },
  methods: {
    close() {
      this.$emit('close')
    },
  },
}
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
</style>
