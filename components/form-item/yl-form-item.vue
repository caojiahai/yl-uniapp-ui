<template>
  <view class="yl-form-item">
    <view class="form-item">
      <view class="item-label">
        <text v-if="required">*</text>
        {{ title }}
      </view>
      <view
        :style="{ justifyContent: justifyContent }"
        class="item-content"
        @click="click"
      >
        <text :class="value ? 'item-value' : 'item-placeholder'">
          {{ value ? value : placeholder }}
        </text>
        <view class="item-icon">
          <u-icon
            v-if="rightIcon"
            color="#999999"
            name="arrow-right"
            size="14"
          />
        </view>
      </view>
    </view>
    <template>
      <slot name="extend"></slot>
    </template>
  </view>
</template>
<script>
export default {
  name: 'yl-form-item',
  props: {
    // 标题
    title: {
      type: String,
      default: '标题',
    },
    // 默认值
    defaultValue: {
      type: String,
      default: '',
    },
    // placeholder
    placeholder: {
      type: String,
      default: '请选择',
    },
    // 是否必填，显示*
    required: {
      type: Boolean,
      default: false,
    },
    // 是否显示右侧显示向右箭头
    rightIcon: {
      type: Boolean,
      default: true,
    },
    // flex justify-content 排列方式
    justifyContent: {
      type: String,
      default: 'space-between',
    },
  },
  computed: {},
  mounted() {
    this.value = this.defaultValue
  },
  watch: {
    defaultValue: {
      handler(val) {
        this.value = val
      },
      deep: true,
    },
  },
  data() {
    return {
      value: '', // 当前选中
    }
  },
  methods: {
    click() {
      this.$emit('itemClick')
    },
  },
}
</script>
<style lang="scss" scoped>
.yl-form-item {
  background-color: #ffffff;

  .form-item {
    display: flex;
    align-items: center;
    min-height: 96rpx;

    .item-label {
      width: 144rpx;
      font-size: 28rpx;
      color: #666666;

      text {
        color: #ff3131;
      }
    }

    .item-content {
      flex: 1;
      display: flex;
      align-items: center;
      overflow: hidden;
      margin-left: 24rpx;

      .item-placeholder {
        font-size: 30rpx;
        color: #999999;
      }

      .item-value {
        font-size: 30rpx;
        color: #333333;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
      }

      .item-icon {
        margin-left: 8rpx;
        min-width: 20px;
        width: 20px;
        height: 20px;
        display: flex;
        align-items: center;
        justify-content: center;
      }
    }
  }
}
</style>
