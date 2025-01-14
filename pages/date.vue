<template>
  <view className="home">
    <u-navbar :autoBack="true" title="日期" />
    <view style="margin-top: 44px; padding: 24rpx; background-color: #f8f8f8">
      <yl-default-card>
        <yl-custom-date
          :default-value="date"
          :show="show"
          @cancel="show = false"
          @confirm="confirm"
        >
          <template #content>
            <view @click="show = true">{{ date }}</view>
          </template>
        </yl-custom-date>
      </yl-default-card>
    </view>
  </view>
</template>
<script>
import YlDefaultCard from '@/components/card/yl-default-card.vue'
import YlCustomDate from '@/components/date/yl-custom-date.vue'

export default {
  components: {
    YlCustomDate,
    YlDefaultCard,
  },
  data() {
    return {
      show: false,
      date: '2024-11-29',
    }
  },
  methods: {
    confirm(val) {
      console.log('confirm:', val)
      this.date = val
      this.show = false
    },
  },
}
</script>
<style scoped>
.home {
  height: 100vh;
  background-color: #f8f8f8;
}
</style>
