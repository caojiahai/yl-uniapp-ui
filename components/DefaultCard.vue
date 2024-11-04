<template>
  <view :style="customStyle" class="card">
    <view v-if="title" class="title">
      <view class="title_header">
        <view class="text">{{ title }}</view>
      </view>
    </view>
    <view :style="{gap: `${gutter}rpx`}" class="content">
      <slot></slot>
    </view>
  </view>
</template>
<script>
export default {
  name: "DefaultCard",
  computed: {},
  components: {},
  props: {
    title: {
      type: String,
      default: ''
    },
    gutter: 0,
    customStyle: ''
  },
  data() {
    return {};
  },
  methods: {}
};
</script>
<style lang="scss" scoped>
.card {
  background-color: #ffffff;
  border-radius: 24rpx;
  padding: 24rpx;
  //margin: 24rpx;

  .content {
    display: flex;
    flex-direction: column;
  }

  .title {
    .title_header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      height: 96rpx;

      .text {
        font-size: 32rpx;
        color: #111111;
        margin-top: 6rpx;
        margin-bottom: 30rpx;
      }
    }
  }
}
</style>
