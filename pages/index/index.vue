<template>
  <view class="home">
    <u-navbar
      :autoBack="false"
      leftIcon=""
      title="首页"
    >
    </u-navbar>
    <view style="margin-top: 44px">
      <yl-select-filter
        :item-list="planSelectFilter"
        @confirm="confirmSelect"
      />
    </view>
  </view>
</template>

<script>
import DefaultCard from "@/components/DefaultCard.vue";
import YlSelectFilter from "@/components/yl-select-filter.vue";

export default {
  components: {YlSelectFilter, DefaultCard},
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
