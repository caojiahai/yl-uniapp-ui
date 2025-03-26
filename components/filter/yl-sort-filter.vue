<template>
  <view class="yl-sort-filter">
    <view class="sort_btn" @tap.stop="sortChange">
      <text>{{ title || '排序' }}</text>
      <view>
        <u-icon
          :color="sort === 'asc' ? '#333333' : '#999999'"
          name="arrow-up-fill"
          size="8"
        />
        <u-icon
          :color="sort === 'desc' ? '#333333' : '#999999'"
          name="arrow-down-fill"
          size="8"
        />
      </view>
    </view>
  </view>
</template>
<script>
export default {
  name: 'yl-sort-filter',
  computed: {},
  components: {},
  props: {
    // 按钮文本
    title: {
      type: String,
      default: '',
    },
    // 默认排序
    defaultSort: {
      type: String,
      default: '',
    },
  },
  watch: {
    defaultSort: {
      handler() {
        this.sort = this.defaultSort
      },
      deep: true,
    },
  },
  mounted() {
    this.sort = this.defaultSort
  },
  data() {
    return {
      sort: '', // asc、desc
    }
  },
  methods: {
    sortChange() {
      switch (this.sort) {
        case 'asc':
          this.sort = 'desc'
          break
        case 'desc':
          this.sort = ''
          break
        default:
          this.sort = 'asc'
          break
      }
      this.$emit('change', this.sort)
    },
  },
}
</script>
<style lang="scss" scoped>
.yl-sort-filter {
  .sort_btn {
    display: flex;
    align-items: center;
    gap: 8rpx;
    padding: 16rpx 32rpx;
    height: 48rpx;
    background-color: #ffffff;
    border-radius: 24rpx;
    color: #333333;
    width: fit-content;
    white-space: nowrap;
  }
}
</style>
