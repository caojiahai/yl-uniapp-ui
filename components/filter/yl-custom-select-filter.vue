<template>
  <view class="yl-custom-select-filter">
    <template>
      <slot name="content"></slot>
    </template>
    <u-picker
      ref="uPicker"
      :cancelText="cancelText || '重置'"
      :closeOnClickOverlay="true"
      :columns="columns"
      :confirmText="confirmText || '确定'"
      :keyName="keyName || 'label'"
      :show="show"
      @cancel="cancel"
      @close="close"
      @confirm="confirm"
    />
  </view>
</template>
<script>
export default {
  name: 'yl-custom-select-filter',
  computed: {},
  components: {},
  props: {
    // 是否显示
    show: {
      type: Boolean,
      default: false,
    },
    // 传入列表
    itemList: {
      type: Array,
      default: [],
    },
    // 取消按钮文本
    cancelText: {
      type: String,
      default: '',
    },
    // 确认按钮文本
    confirmText: {
      type: String,
      default: '',
    },
    // keyName
    keyName: {
      type: String,
      default: '',
    },
    // defaultIndex
    defaultIndex: {
      type: Number,
      default: 0,
    },
  },
  watch: {
    itemList: {
      handler() {
        this.columns = [[...(this.itemList || [])]]
      },
      deep: true,
    },
  },
  mounted() {
    this.columns = [[...(this.itemList || [])]]
  },
  data() {
    return {
      columns: [],
    }
  },
  methods: {
    close() {
      this.$emit('close')
    },
    cancel() {
      this.$refs.uPicker.setIndexs([this.defaultIndex])
      this.$emit('cancel')
    },
    confirm(e) {
      this.$emit('confirm', e?.value?.[0])
    },
  },
}
</script>
<style lang="scss" scoped>
.yl-custom-select-filter {
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
