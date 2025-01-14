<template>
  <view class="yl-custom-popup-filter">
    <template>
      <slot name="content"></slot>
    </template>
    <u-popup
      :mode="popupMode"
      :round="popupRound"
      :show="show"
      closeOnClickOverlay
      @close="close"
    >
      <template>
        <slot name="popup"></slot>
      </template>
    </u-popup>
  </view>
</template>
<script>
export default {
  name: 'yl-custom-popup-filter',
  computed: {},
  components: {},
  props: {
    // 是否显示
    show: {
      type: Boolean,
      default: false,
    },
    // popup mode
    popupMode: {
      type: String,
      default: 'bottom',
    },
    // popup round
    popupRound: {
      type: Number,
      default: 0,
    },
    // popup show
    popupShow: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {}
  },
  methods: {
    close() {
      this.$emit('close')
    },
  },
}
</script>
<style lang="scss" scoped>
.yl-custom-popup-filter {
}
</style>
