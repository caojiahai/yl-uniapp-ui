<template>
  <view class="yl-custom-filter">
    <template>
      <slot name="content"></slot>
    </template>
    <view v-if="show" :style="{ height: `calc(100vh - ${bgHeight}rpx)` }" class="item_popup_bg" @click="close"/>
    <view v-if="show" class="item_popup">
      <template>
        <slot name="popup"></slot>
      </template>
    </view>
  </view>
</template>
<script>
export default {
  name: "yl-custom-filter",
  components: {},
  props: {
    // 是否显示
    show: {
      type: Boolean,
      default: false
    },
    // 背景高度
    bgHeight: {
      type: Number,
      default: 0
    }
  },
  data() {
    return {};
  },
  mounted() {
  },
  watch: {},
  computed: {},
  methods: {
    close() {
      this.$emit("close")
    }
  }
};
</script>
<style lang="scss" scoped>
.yl-custom-filter {
  position: relative;

  .item_popup_bg {
    position: absolute;
    width: 100%;
    background-color: rgba(0, 0, 0, 0.2);
    z-index: 99;
  }

  .item_popup {
    position: absolute;
    left: 0;
    right: 0;
    background-color: #ffffff;
    z-index: 100;
  }
}
</style>
