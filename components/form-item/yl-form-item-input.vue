<template>
  <view class="yl-form-item-input">
    <view class="form-item">
      <view class="item-label">
        <text v-if="required">*</text>
        {{ title }}
      </view>
      <view :style="{ justifyContent: justifyContent }" class="item-content">
        <u-input
          v-model="value"
          :placeholder="placeholder"
          border="none"
          @change="(val) => $emit('change', val)"
        />
      </view>
    </view>
  </view>
</template>
<script>
export default {
  name: 'yl-form-item-input',
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
      default: '请输入',
    },
    // 是否必填，显示*
    required: {
      type: Boolean,
      default: false,
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
.yl-form-item-input {
  background-color: #ffffff;

  .uni-input-placeholder,
  .input-placeholder {
    color: #999999 !important;
  }

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
