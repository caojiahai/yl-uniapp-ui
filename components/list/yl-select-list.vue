<template>
  <view class="yl-select-list">
    <text :class="selected ? 'text-selected' : 'text-un-select'" class="text-ellipsis ">
      {{ value }}
    </text>
    <view class="text-icon">
      <u-icon v-if="selected" color="#ff9438" name="checkmark-circle-fill" size="20"/>
    </view>
  </view>
</template>
<script>
export default {
  name: "yl-select-list",
  computed: {},
  components: {},
  props: {
    // 是否选中
    selected: {
      type: Boolean,
      default: false
    },
    value: {
      type: String,
      default: ""
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
.yl-select-list {
  height: 88rpx;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 32rpx;
  overflow: hidden;

  .text-icon {
    margin-left: 24rpx;
    width: 40rpx;
    min-width: 40rpx;
    max-width: 40rpx;
  }

  .text-un-select {
    color: #333333;
    font-size: 28rpx;
  }

  .text-selected {
    color: #FF9438;
    font-size: 28rpx;
  }

  .text-ellipsis {
    text-overflow: ellipsis;
    overflow: hidden;
    white-space: nowrap;
  }
}
</style>
