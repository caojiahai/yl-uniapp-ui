<template>
  <view class="yl-select-filter">
    <view class="filter_btn" @tap.stop="show = true">
      <text>{{ title || '选择' }}</text>
      <u-icon :name="iconName || 'arrow-down'" color="#999999" size="12"/>
    </view>
    <u-picker
      ref="uPicker"
      :cancelText="cancelText || '重置'"
      :closeOnClickOverlay="true"
      :columns="columns"
      :confirmText="confirmText || '确定'"
      :keyName="keyName || 'label'"
      :show="show"
      @cancel="cancel"
      @close="show = false"
      @confirm="confirm"
    />
  </view>
</template>
<script>
export default {
  name: "yl-select-filter",
  computed: {},
  components: {},
  props: {
    // 按钮文本
    title: {
      type: String,
      default: ""
    },
    // 传入列表
    itemList: {
      type: String,
      default: ""
    },
    // 取消按钮文本
    cancelText: {
      type: String,
      default: ""
    },
    // 确认按钮文本
    confirmText: {
      type: String,
      default: ""
    },
    // 图标name
    iconName: {
      type: String,
      default: ""
    },
    // keyName
    keyName: {
      type: String,
      default: ""
    },
  },
  watch: {
    'itemList': {
      handler() {
        this.columns = [[...this.itemList || []]];
      },
      deep: true
    },
  },
  mounted() {
    this.columns = [[...this.itemList || []]];
  },
  data() {
    return {
      show: false,
      defaultIndex: 0,
      columns: [],
    };
  },
  methods: {
    cancel() {
      this.show = false;
      this.$refs.uPicker.setIndexs([this.defaultIndex]);
      this.$emit('confirm', this.columns?.[this.defaultIndex]?.[this.defaultIndex])
    },
    confirm(e) {
      this.show = false;
      this.$emit('confirm', e?.value?.[0])
    }
  }
};
</script>
<style lang="scss" scoped>
.yl-select-filter {
  .filter_btn {
    display: flex;
    align-items: center;
    gap: 8rpx;
    padding: 16rpx 32rpx;
    height: 48rpx;
    background-color: #ffffff;
    border-radius: 24rpx;
    color: #333333;
    width: fit-content;
  }
}
</style>
