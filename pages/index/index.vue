<template>
  <view class="home">
    <u-navbar
      :autoBack="false"
      leftIcon=""
      title="首页"
    >
    </u-navbar>
    <view style="margin-top: 44px">
      <view style="display: flex; align-items: center;">
        <yl-sort-filter title="日期"/>
        <yl-select-filter
          :item-list="planSelectFilter"
          @confirm="confirmSelect"
        />
      </view>
    </view>
  </view>
</template>

<script>
import YlSelectFilter from "@/components/yl-select-filter.vue";
import YlSortFilter from "@/components/yl-sort-filter.vue";

export default {
  components: {YlSortFilter, YlSelectFilter},
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
    confirmSelect(val) {
      console.log(val);
    }
  }
}
</script>

<style>
.home {

}
</style>
