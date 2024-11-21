<template>
  <view class="home">
    <u-navbar
      :autoBack="false"
      leftIcon=""
      title="首页"
    />
    <view style="margin-top: 44px">
      <yl-popup-filter @cancel="cancelFilter" @confirm="confirmFilter">
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

export default {
  components: {YlPopupFilter, YlDefaultCard, YlSortFilter, YlSelectFilter},
  data() {
    return {
      title: '',
      planSelectFilter: [{label: '全部订单', id: ''}]
    }
  },
  onLoad() {
    let t = this;
    setTimeout(function () {
      t.planSelectFilter.push({label: '订单1', id: '1'})
    }, 2000)
  },
  methods: {
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
