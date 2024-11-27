<template>
  <view class="yl-custom-date">
    <template>
      <slot name="content"></slot>
    </template>
    <u-datetime-picker
      v-model="value"
      :show="show"
      mode="date"
      @cancel="cancel"
      @confirm="confirm"
    />
  </view>
</template>
<script>
import dayjs from "dayjs";

export default {
  name: "yl-custom-date",
  computed: {},
  components: {},
  props: {
    // 是否显示
    show: {
      type: Boolean,
      default: false
    },
    // 默认显示日期
    defaultValue: {
      type: String,
      default: '',
    },
  },
  watch: {
    'defaultValue': {
      handler(newVal) {
        this.value = dayjs(newVal).valueOf();
      },
      deep: true
    }
  },
  data() {
    return {
      value: dayjs(this.defaultValue ?? '').valueOf()
    };
  },
  methods: {
    cancel() {
      this.$emit('cancel');
    },
    confirm(e) {
      this.$emit('confirm', dayjs(e.value).format('YYYY-MM-DD'));
    },
  }
};
</script>
<style lang="scss" scoped>
.yl-custom-date {
}
</style>
