<template>
  <text :style="{
    color: `${color}`,
    background: `${bgColor}`
  }" class="yl-default-tag" @click="tagClick">
    {{ title }}
  </text>
</template>
<script>
export default {
  name: "yl-default-tag",
  computed: {},
  components: {},
  props: {
    // 标题
    title: {
      type: String,
      default: "标签"
    },
    // 颜色
    color: {
      type: String,
      default: "#3F94FF"
    },
    // 背景颜色
    bgColor: {
      type: String,
      default: "#3F94FF1A"
    }
  },
  data() {
    return {};
  },
  methods: {
    tagClick() {
      this.$emit('click')
    }
  }
};
</script>
<style lang="scss" scoped>
.yl-default-tag {
  padding: 4rpx 12rpx;
  height: 30rpx;
  line-height: 30rpx;
  font-size: 22rpx;
  border-radius: 8rpx;
  white-space: nowrap;
}
</style>
