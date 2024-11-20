<template>
  <view class="yl-no-padding-card">
    <slot></slot>
  </view>
</template>
<script>
export default {
  name: "yl-no-padding-card",
  computed: {},
  components: {},
  props: {},
  data() {
    return {};
  },
  methods: {}
};
</script>
<style lang="scss" scoped>
.yl-no-padding-card {
  background-color: #ffffff;
  border-radius: 24rpx;
  overflow: hidden;
}
</style>
