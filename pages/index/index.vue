<template>
  <view class="home">
    <u-navbar
      :autoBack="false"
      leftIcon=""
      title="首页"
    >
    </u-navbar>
    <view style="margin-top: 44px">
      <yl-sort-filter title="排序"/>
      <yl-select-filter
        :item-list="planSelectFilter"
        @confirm="confirmSelect"
      />
      <yl-default-card title="标题标题标题标题标题标题标题标题标题标题标题标题标题标题">
        <view>12321</view>
      </yl-default-card>
    </view>
  </view>
</template>
<script>
import YlSelectFilter from "@/components/filter/yl-select-filter.vue";
import YlSortFilter from "@/components/filter/yl-sort-filter.vue";
import YlDefaultCard from "@/components/card/yl-default-card.vue";

export default {
  components: {YlDefaultCard, YlSortFilter, YlSelectFilter},
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
  height: 100vh;
  background-color: #f8f8f8;
}
</style>
