<template>
  <view class="yl-count-down">
    <view
      v-for="(x, index) in countDays"
      :key="`${index + 'day'}`"
      class="box"
    >
      {{ x }}
    </view>
    <view class="text">天</view>
    <view
      v-for="(x, index) in countHours"
      :key="`${index + 'hour'}`"
      class="box"
    >
      {{ x }}
    </view>
    <view class="text">时</view>
    <view
      v-for="(x, index) in countMinutes"
      :key="`${index + 'minutes'}`"
      class="box"
    >
      {{ x }}
    </view>
    <view class="text">分</view>
    <view
      v-for="(x, index) in countSeconds"
      :key="`${index + 'second'}`"
      class="box"
    >
      {{ x }}
    </view>
    <view class="text">秒</view>
  </view>
</template>
<script>
import dayjs from "dayjs";

export default {
  name: "yl-count-down",
  props: {
    // 倒计时结束时间
    endTime: {
      type: String,
      default: "",
    },
  },
  data() {
    return {
      countDays: ["0", "0"],
      countHours: ["0", "0"],
      countMinutes: ["0", "0"],
      countSeconds: ["0", "0"],
      timer: null, // 倒计时
      show: false, // 是否显示
    };
  },
  mounted() {
    clearInterval(this.timer);
    this.getDateCountDown();
  },
  unmounted() {
    clearInterval(this.timer);
  },
  methods: {
    updateCount() {
      if (!this.endTime) return false;
      if (dayjs().isAfter(this.endTime)) return false;
      const countDownDate = dayjs(this.endTime).valueOf();
      const now = new Date().getTime();
      const distance = countDownDate - now;

      this.show = distance > 0;

      // 时间计算
      const days = Math.floor(distance / (1000 * 60 * 60 * 24));
      const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((distance % (1000 * 60)) / 1000);

      this.countDays = (days < 10 ? `0${days}` : `${days}`).split("");
      this.countHours = (hours < 10 ? `0${hours}` : `${hours}`).split("");
      this.countMinutes = (minutes < 10 ? `0${minutes}` : `${minutes}`).split("");
      this.countSeconds = (seconds < 10 ? `0${seconds}` : `${seconds}`).split("");

      // 如果倒计时结束，写一些文本
      if (distance < 0) {
        clearInterval(this.timer);
      }
    },
    getDateCountDown() {
      let t = this;
      clearInterval(this.timer);
      t.updateCount();
      // 更新倒计时每一秒
      this.timer = setInterval(() => {
        t.updateCount();
      }, 1000);
    },
  },
};
</script>
<style lang="scss" scoped>
.yl-count-down {
  display: flex;
  align-items: center;
  justify-content: flex-end;

  & > view {
    margin-left: 8rpx;

    &:first-child {
      margin-left: 0;
    }
  }

  .box {
    width: 30rpx;
    height: 34rpx;
    background-color: #ff5334;
    color: #ffffff;
    text-align: center;
    line-height: 34rpx;
    font-size: 24rpx;
    border-radius: 4rpx;
  }

  .text {
    color: #333333;
    font-size: 24rpx;
  }
}
</style>
