<template>
  <view class="home">
    <u-navbar
      :autoBack="false"
      leftIcon=""
      title="首页"
    />
    <view style="margin-top: 44px">
      <view style="display: flex;background-color: #ffffff;gap: 20rpx;flex-wrap: wrap;">
        <yl-tag v-for="(x, index) in [1,2,3,4,5,6]" :key="index" :name="index" :selected="currentIndex === index"
                @tagClick="tagClick"/>
      </view>
      <yl-popup-filter :popup-width="100" @cancel="cancelFilter" @confirm="confirmFilter">
        <view>111</view>
        <view>222</view>
      </yl-popup-filter>
    </view>
  </view>
</template>
<script>
import YlSelectFilter from "@/components/filter/yl-select-filter.vue";
import YlSortFilter from "@/components/filter/yl-sort-filter.vue";
import YlDefaultCard from "@/components/card/yl-default-card.vue";
import YlPopupFilter from "@/components/filter/yl-popup-filter.vue";
import YlTag from "@/components/tag/yl-tag.vue";

export default {
  components: {YlTag, YlPopupFilter, YlDefaultCard, YlSortFilter, YlSelectFilter},
  data() {
    return {
      title: '',
      planSelectFilter: [{label: '全部订单', id: ''}],
      currentIndex: 0
    }
  },
  onLoad() {
    let t = this;
    setTimeout(function () {
      t.planSelectFilter.push({label: '订单1', id: '1'})
    }, 2000)
  },
  methods: {
    tagClick(val) {
      this.currentIndex = val;
      console.log(val)
    },
    cancelFilter() {
      console.log(111)
    },
    confirmFilter() {
      console.log(222);
    }
  }
}
</script>
<style>
.home {
  height: 100vh;
  background-color: #f8f8f8;
}
</style>
