<template>
  <view
    :style="{ color: color, fontSize: size }"
    class="yl-ellipsis"
    @click="ellipsisClick"
  >
    <view class="ellipsis-text">{{ value }}</view>
    <view v-if="suffixCount > 0" class="ellipsis-suffix">{{ suffix }}</view>
  </view>
</template>
<script>
export default {
  name: 'yl-ellipsis',
  computed: {},
  components: {},
  props: {
    // 文本
    text: {
      type: String,
      default: '',
    },
    // 后缀长度
    suffixCount: {
      type: Number,
      default: 0,
    },
    // 颜色
    color: {
      type: String,
      default: '#333333',
    },
    // 大小
    size: {
      type: String,
      default: '28rpx',
    },
  },
  data() {
    return {
      value: '',
      suffix: '',
    }
  },
  mounted() {
    this.handleValue()
  },
  watch: {
    text: {
      handler() {
        this.handleValue()
      },
      deep: true,
    },
    suffixCount: {
      handler() {
        this.handleValue()
      },
      deep: true,
    },
  },
  methods: {
    handleValue() {
      if (this.text) {
        let len = this.text?.length
        this.value = this.text?.substring(0, len - this.suffixCount)
        this.suffix = this.text?.substring(len - this.suffixCount, len)
      }
    },
    ellipsisClick() {
      this.$emit('click')
    },
  },
}
</script>
<style lang="scss" scoped>
.yl-ellipsis {
  display: flex;
  align-items: center;
  overflow: hidden;

  .ellipsis-text {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }

  .ellipsis-suffix {
    white-space: nowrap;
  }
}
</style>
