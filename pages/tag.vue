<template>
  <view class="home">
    <u-navbar :autoBack="true" title="标签展示"/>
    <view style="margin-top: 44px;padding: 24rpx;">
      <yl-default-card>
        <yl-default-tag/>
        <view style="margin-top: 20rpx;"/>
        <yl-tab-tag sub-title="值值值值值" title="标签"/>
        <view style="margin-top: 20rpx;"/>
        <yl-tag :selected="false" title="标签"/>
        <view style="margin-top: 20rpx;"/>
        <yl-tag :selected="true" title="标签"/>
      </yl-default-card>
    </view>
  </view>
</template>
<script>
import YlSelectFilter from "@/components/filter/yl-select-filter.vue";
import YlSortFilter from "@/components/filter/yl-sort-filter.vue";
import YlDefaultCard from "@/components/card/yl-default-card.vue";
import YlPopupFilter from "@/components/filter/yl-popup-filter.vue";
import YlTag from "@/components/tag/yl-tag.vue";
import YlFormItemPopup from "@/components/form-item/yl-form-item-popup.vue";
import YlDefaultHeader from "@/components/header/yl-default-header.vue";
import YlSelectList from "@/components/list/yl-select-list.vue";
import YlCustomFilter from "@/components/filter/yl-custom-filter.vue";
import YlCustomSelectFilter from "@/components/filter/yl-custom-select-filter.vue";
import YlCustomDate from "@/components/date/yl-custom-date.vue";
import YlDefaultProgress from "@/components/progress/yl-default-progress.vue";
import YlCustomPopupFilter from "@/components/filter/yl-custom-popup-filter.vue";
import YlFormItem from "@/components/form-item/yl-form-item.vue";
import YlFormItemInput from "@/components/form-item/yl-form-item-input.vue";
import YlTabTag from "@/components/tag/yl-tab-tag.vue";
import YlCountDown from "@/components/count/yl-count-down.vue";
import YlItemList from "@/components/list/yl-item-list.vue";
import YlItemLayoutList from "@/components/list/yl-item-layout-list.vue";
import YlDefaultTag from "@/components/tag/yl-default-tag.vue";

export default {
  components: {
    YlDefaultTag,
    YlItemLayoutList,
    YlItemList,
    YlCountDown,
    YlTabTag,
    YlFormItemInput,
    YlFormItem,
    YlCustomPopupFilter,
    YlDefaultProgress,
    YlCustomDate,
    YlCustomSelectFilter,
    YlCustomFilter,
    YlSelectList,
    YlDefaultHeader, YlFormItemPopup, YlTag, YlPopupFilter, YlDefaultCard, YlSortFilter, YlSelectFilter
  },
  data() {
    return {
      title: '',
      planSelectFilter: [{label: '全部订单', id: ''}],
      currentIndex: 0,
      show: false,
      show1: false
    }
  },
  onLoad() {
    let t = this;
    setTimeout(function () {
      t.planSelectFilter.push({label: '订单1', id: '1'})
    }, 2000)
  },
  methods: {
    cancel() {
      // this.show = false;
    },
    confirm(val) {
      console.log(val)
      this.show = true;
    },
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
