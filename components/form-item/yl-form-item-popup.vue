<template>
  <view class="yl-form-item-popup">
    <view class="form-item">
      <view class="item-label">
        <text v-if="required">*</text>
        {{ title }}
      </view>
      <view :style="{ justifyContent: justifyContent }" class="item-content" @click="show = true">
        <text :class="value ? 'item-value': 'item-placeholder'">
          {{ value ? value : placeholder }}
        </text>
        <u-icon v-if="rightIcon" color="#999999" name="arrow-right" size="20" style="margin-left: 8rpx"/>
      </view>
    </view>
    <u-popup :mode="popupMode" :round="popupRound" :show="show" closeOnClickOverlay @close="close">
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
    }
  },
  computed: {},
  mounted() {
  },
  watch: {
    // 'itemList': {
    //   handler(val) {
    //     this.dataList = _.cloneDeep(val);
    //     this.value = this.itemList?.filter(x => x?.selected)?.map(x => x?.name)?.join('、');
    //   },
    //   deep: true
    // }
  },
  data() {
    return {
      value: '', // 当前选中
      // dateList: getDateList(), // 日期与时间段
      // dateIndex: 0, // 当前选中日期下标
      show: false,
      // dataList: _.cloneDeep(this.itemList),
    };
  },
  methods: {
    close() {
      this.show = false;
    },
    // changeSelect(val) {
    //   this.dataList[val].selected = !this.dataList[val].selected;
    // },
    // sureTime() {
    //   this.show = false;
    //   this.value = this.itemList?.filter(x => x?.selected)?.map(x => x?.name)?.join('、');
    //   this.$emit('change', this.dataList);
    // },
  }
};
</script>
<style lang="scss" scoped>
.yl-form-item-popup {
  background-color: #ffffff;

  .form-item {
    display: flex;
    align-items: center;
    padding: 0 32rpx;
    min-height: 96rpx;

    .item-label {
      width: 144rpx;
      font-size: 28rpx;

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
    }
  }
}

.door_popup {
  .door_popup_header {
    background-color: #F9F9F9;
    height: 112rpx;
    border-bottom: 1rpx solid #DDDDDD;
    display: flex;
    align-items: center;
    padding: 0 32rpx;

    .header_left {
      width: 200rpx;
      font-size: 32rpx;
      color: #999999;
    }

    .header_title {
      flex: 1;
      font-size: 36rpx;
      color: #000000;
      text-align: center;
    }

    .header_right {
      width: 200rpx;
      font-size: 32rpx;
      color: #14191E;
      text-align: right;
    }
  }

  .door_popup_body {
    overflow-y: auto;
    max-height: 528rpx;
    min-height: 528rpx;

    .item_list_empty {
      display: flex;
      align-items: center;
      justify-content: center;
      color: #999999;
      font-size: 24rpx;
      height: 88rpx;
    }

    .item_list_selected {
      display: flex;
      align-items: center;
      justify-content: space-between;
      height: 88rpx;
      gap: 24rpx;
      padding: 0 48rpx;
      overflow: hidden;

      .item_name {
        color: #FF9438;
        font-size: 28rpx;
        text-overflow: ellipsis;
        overflow: hidden;
        white-space: nowrap;
      }

      .time_icon {
        opacity: 1;
        width: 40rpx;
        min-width: 40rpx;
        height: 40rpx;
        background-repeat: no-repeat;
        //background-image: url("../../static/order/icon_selected.png");
        background-size: cover;
        background-position: center;
      }
    }

    .item_list {
      display: flex;
      align-items: center;
      justify-content: space-between;
      height: 88rpx;
      gap: 24rpx;
      padding: 0 48rpx;
      overflow: hidden;

      .item_name {
        color: #333333;
        font-size: 28rpx;
        text-overflow: ellipsis;
        overflow: hidden;
        white-space: nowrap;
      }

      .time_icon {
        opacity: 0;
      }
    }

    .times {
      display: flex;

      .times_left {
        width: 260rpx;
        background-color: #F3F3F3;

        .time_item {
          height: 96rpx;
          display: flex;
          align-items: center;
          justify-content: center;
          background-color: #F3F3F3;
          font-size: 30rpx;
          color: #333333;
        }

        .time_item_selected {
          color: #FF9438;
          background-color: #ffffff;
        }
      }

      .times_right {
        flex: 1;
        overflow-y: auto;
        height: 672rpx;

        .time_item {
          color: #333333;
          height: 96rpx;
          display: flex;
          align-items: center;
          padding: 0 32rpx;
          justify-content: space-between;
          font-size: 28rpx;

          .time_icon {
            opacity: 0;
          }
        }

        .time_selected {
          color: #FF9438;
          font-size: 30rpx;

          .time_icon {
            opacity: 1;
            width: 40rpx;
            height: 40rpx;
            background-repeat: no-repeat;
            //background-image: url("../../static/order/icon_selected.png");
            background-size: cover;
            background-position: center;
          }
        }
      }
    }
  }
}
</style>
