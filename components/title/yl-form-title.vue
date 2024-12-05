<template>
  <view :style="{ height: titleHeight }" class="yl-form-title">
    <view class="title-left">
      <view class="title">
        {{ title }}
        <text v-if="required" style="color: #FF4910;margin-left: 8rpx;">*</text>
      </view>
    </view>
    <template>
      <slot name="content"></slot>
    </template>
  </view>
</template>
<script>
export default {
  name: "yl-form-title",
  computed: {},
  components: {},
  props: {
    // 标题
    title: {
      type: String,
      default: ""
    },
    // 高度
    titleHeight: {
      type: String,
      default: '60rpx'
    },
    // 是否必填，显示*
    required: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {};
  },
  methods: {}
};
</script>
<style lang="scss" scoped>
.yl-form-title {
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
