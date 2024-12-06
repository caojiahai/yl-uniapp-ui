<template>
  <view :style="{ height: `${itemHeight}` }" class="yl-item-list">
    <view class="item-label">{{ label }}</view>
    <view v-if="value" class="item-value item-ellipsis">{{ value }}</view>
    <template>
      <slot name="content"></slot>
    </template>
  </view>
</template>
<script>
export default {
  name: "yl-item-list",
  computed: {},
  components: {},
  props: {
    // 标签名称
    label: {
      type: String,
      default: ""
    },
    // 默认值
    value: {
      type: String,
      default: ""
    },
    // 高度
    itemHeight: {
      type: String,
      default: '72rpx'
    },
  },
  data() {
    return {};
  },
  methods: {
    click() {
      this.$emit('listClick', this.name ?? '')
    }
  }
};
</script>
<style lang="scss" scoped>
.yl-item-list {
  display: flex;
  align-items: center;
  justify-content: space-between;
  overflow: hidden;

  .item-label {
    color: #666666;
    font-size: 28rpx;
    line-height: 40rpx;
    margin-right: 24rpx;
    white-space: nowrap;
  }

  .item-value {
    color: #111111;
    font-size: 30rpx;
    line-height: 40rpx;
  }

  .item-ellipsis {
    text-overflow: ellipsis;
    overflow: hidden;
    white-space: nowrap;
  }
}
</style>
