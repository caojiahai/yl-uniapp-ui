<template>
  <view class="yl-form-item-popup">
    <view class="form-item">
      <view class="item-label">
        <text v-if="required">*</text>
        {{ title }}
      </view>
      <view :style="{ justifyContent: justifyContent }" class="item-content" @click="showPopup">
        <text :class="value ? 'item-value': 'item-placeholder'">
          {{ value ? value : placeholder }}
        </text>
        <view class="item-icon">
          <u-icon v-if="rightIcon" color="#999999" name="arrow-right" size="14"/>
        </view>
      </view>
    </view>
    <u-popup :mode="popupMode" :round="popupRound" :show="show" closeOnClickOverlay @close="closePopup">
      <slot></slot>
    </u-popup>
  </view>
</template>
<script>
export default {
  name: "yl-form-item-popup",
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
      default: 'justify-content',
    },
    // popup mode
    popupMode: {
      type: String,
      default: 'bottom',
    },
    // popup round
    popupRound: {
      type: Number,
      default: 0
    },
    // popup show
    popupShow: {
      type: Boolean,
      default: false
    }
  },
  computed: {},
  mounted() {
    this.show = this.popupShow;
    this.value = this.defaultValue;
  },
  watch: {
    'popupShow': {
      handler(val) {
        this.show = val;
      },
      deep: true
    },
    'defaultValue': {
      handler(val) {
        this.value = val;
      },
      deep: true
    }
  },
  data() {
    return {
      value: '', // 当前选中
      show: false,
    };
  },
  methods: {
    showPopup() {
      this.$emit('showPopup');
    },
    closePopup() {
      this.$emit('closePopup')
    },
  }
};
</script>
<style lang="scss" scoped>
.yl-form-item-popup {
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
        color: #FF3131;
        margin-right: 4rpx;
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
