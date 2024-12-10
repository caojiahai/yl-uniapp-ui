<template>
  <view
    :class="`${selected ? 'yl-tag-selected' : 'yl-tag-unselected'} ${ellipsis ? '' : 'yl-tag-ellipsis'}`"
    :style="{ width: `${width}`, padding: noPadding ? 0 : '0 40rpx' }"
    class="yl-tag"
    @click="click"
  >
    {{ title || '默认标签' }}
  </view>
</template>
<script>
export default {
  name: "yl-tag",
  computed: {},
  components: {},
  props: {
    // 标题
    title: {
      type: String,
      default: ""
    },
    // 是否超出隐藏、默认超出隐藏
    ellipsis: {
      type: Boolean,
      default: false
    },
    // 是否隐藏
    selected: {
      type: Boolean,
      default: false
    },
    // 标签标识
    name: {
      type: String | Number,
      default: ""
    },
    // 标签宽度
    width: {
      type: String,
      default: ""
    },
    // 无padding
    noPadding: {
      type: Boolean,
      default: false
    },
  },
  data() {
    return {};
  },
  methods: {
    click() {
      this.$emit('tagClick', this.name ?? '')
    }
  }
};
</script>
<style lang="scss" scoped>
.yl-tag {
  text-align: center;
  min-width: 152rpx;
  padding: 0 40rpx;
  width: fit-content;
  border-radius: 4rpx;
  box-sizing: border-box;
  font-size: 26rpx;
  line-height: 58rpx;
}

.yl-tag-unselected {
  background-color: #f6f6f6;
  border: 1rpx solid #f6f6f6;
  color: #111111;
}

.yl-tag-selected {
  background-color: #FF94381A;
  border: 1rpx solid #ff9438;
  color: #ff9438;
}

.yl-tag-ellipsis {
  text-overflow: ellipsis;
  overflow: hidden;
  white-space: nowrap;
}
</style>
