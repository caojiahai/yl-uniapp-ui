<template>
  <view
    :style="{ height: `${itemHeight}` }"
    class="yl-default-list"
    @tap="click"
  >
    <view class="item-title">{{ title }}</view>
    <view class="item-right">
      <view v-if="value" class="item-value item-ellipsis">{{ value }}</view>
      <view v-if="placeholder" class="item-placeholder">{{ placeholder }}</view>
      <view class="item-icon">
        <u-icon v-if="rightIcon" color="#999999" name="arrow-right" size="14" />
      </view>
    </view>
  </view>
</template>
<script>
export default {
  name: 'yl-default-list',
  computed: {},
  components: {},
  props: {
    // 标签名称
    title: {
      type: String,
      default: '',
    },
    // 默认值
    value: {
      type: String,
      default: '',
    },
    // 高度
    itemHeight: {
      type: String,
      default: '96rpx',
    },
    // 是否显示右侧显示向右箭头
    rightIcon: {
      type: Boolean,
      default: true,
    },
    // placeholder
    placeholder: {
      type: String,
      default: '',
    },
  },
  data() {
    return {}
  },
  methods: {
    click() {
      this.$emit('listClick')
    },
  },
}
</script>
<style lang="scss" scoped>
.yl-default-list {
  display: flex;
  align-items: center;
  justify-content: space-between;
  overflow: hidden;

  .item-title {
    color: #666666;
    font-size: 28rpx;
    line-height: 40rpx;
    margin-right: 24rpx;
  }

  .item-right {
    display: flex;
    align-items: center;

    .item-icon {
      margin-left: 8rpx;
      min-width: 20px;
      width: 20px;
      height: 20px;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .item-placeholder {
      color: #999999;
      font-size: 30rpx;
      line-height: 40rpx;
    }

    .item-value {
      color: #333333;
      font-size: 30rpx;
      line-height: 40rpx;
    }

    .item-ellipsis {
      text-overflow: ellipsis;
      overflow: hidden;
      white-space: nowrap;
    }
  }
}
</style>
