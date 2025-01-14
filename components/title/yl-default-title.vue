<template>
  <view :style="{ height: titleHeight }" class="yl-default-title">
    <view class="title-left">
      <view class="title">{{ title }}</view>
      <template>
        <slot name="extend"></slot>
      </template>
    </view>
    <template>
      <slot name="content"></slot>
    </template>
  </view>
</template>
<script>
export default {
  name: 'yl-default-title',
  computed: {},
  components: {},
  props: {
    // 标题
    title: {
      type: String,
      default: '',
    },
    // 高度
    titleHeight: {
      type: String,
      default: '60rpx',
    },
  },
  data() {
    return {}
  },
  methods: {},
}
</script>
<style lang="scss" scoped>
.yl-default-title {
  display: flex;
  align-items: center;
  justify-content: space-between;

  .title-left {
    display: flex;
    align-items: center;
    overflow: hidden;

    .title {
      font-size: 34rpx;
      color: #111111;
      line-height: 60rpx;
      font-weight: 500;
      overflow: hidden;
      text-overflow: ellipsis;
      white-space: nowrap;
    }
  }
}
</style>
