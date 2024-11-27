<template>
  <view :style="{ padding: noPadding ? 0 : '24rpx' }" class="yl-default-card">
    <view v-if="title" class="card-title">{{ title }}</view>
    <slot></slot>
  </view>
</template>
<script>
export default {
  name: "yl-default-card",
  computed: {},
  components: {},
  props: {
    // 标题
    title: {
      type: String,
      default: ""
    },
    // 无padding
    noPadding: {
      type: Boolean,
      default: false
    },
  },
  data() {
    return {};
  },
  methods: {}
};
</script>
<style lang="scss" scoped>
.yl-default-card {
  background-color: #ffffff;
  padding: 24rpx;
  border-radius: 24rpx;
  overflow: hidden;

  .card-title {
    height: 80rpx;
    line-height: 80rpx;
    font-size: 34rpx;
    color: #111111;
    font-weight: 500;
    text-overflow: ellipsis;
    overflow: hidden;
    white-space: nowrap;
  }
}
</style>
