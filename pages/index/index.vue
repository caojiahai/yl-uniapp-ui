<template>
  <view class="home">
    <u-navbar
      :autoBack="false"
      leftIcon=""
      title="首页"
    />
    <view style="margin-top: 44px; background-color: #f8f8f8;padding: 12px;">
      <!--      <yl-form-item-popup-->
      <!--        :popup-show="show"-->
      <!--        :required="true"-->
      <!--        default-value=""-->
      <!--        justify-content="flex-end"-->
      <!--        title="测试标题"-->
      <!--        @closePopup="show = false"-->
      <!--        @showPopup="show = true"-->
      <!--      >-->
      <!--        <yl-default-header @leftClick="show = false" @rightClick="show = false"/>-->
      <!--        <yl-select-list :icon-name="'checkmark'" :selected="true" value="测试测试"/>-->
      <!--      </yl-form-item-popup>-->


      <!--      <view style="display: flex;background-color: #ffffff;gap: 20rpx;flex-wrap: wrap;">-->
      <!--        <yl-tag v-for="(x, index) in [1,2,3,4,5,6]" :key="index" :name="index" :selected="currentIndex === index"-->
      <!--                @tagClick="tagClick"/>-->
      <!--      </view>-->
      <!--      <yl-popup-filter :popup-width="100" @cancel="cancelFilter" @confirm="confirmFilter">-->
      <!--        <view>111</view>-->
      <!--        <view>222</view>-->
      <!--      </yl-popup-filter>-->
    </view>
    <!--    <yl-custom-select-filter-->
    <!--      :item-list="[{ id: 1, name: '111'}, { id: 2, name: '222'}]"-->
    <!--      :show="show"-->
    <!--      key-name="name"-->
    <!--      @cancel="cancel"-->
    <!--      @close="show = false"-->
    <!--      @confirm="confirm"-->
    <!--    >-->
    <!--      <template #content>-->
    <!--        <view @click="show = true">排序</view>-->
    <!--      </template>-->
    <!--    </yl-custom-select-filter>-->
    <yl-custom-date :default-value="'2024-11-29'" :show="show" @confirm="confirm">
      <template #content>
        <view @click="show = true">111</view>
      </template>
    </yl-custom-date>
    <view>
      <yl-custom-filter :bg-height="182" :popup-round="20" :show="show" @close="show = false">
        <template #content>
          <view style="display: flex;align-items: center;justify-content: space-between;">
            <view @click="show = true">排序</view>
            <yl-popup-filter :show="show1">
              <template #content>
                <view @click="show1 = true">筛选</view>
              </template>
              <template #popup>
                <view @click="show1 = false">111</view>
              </template>
            </yl-popup-filter>
          </view>
        </template>
        <template #popup>
          <view>
            <yl-select-list :icon-name="'checkmark'" :selected="true" value="测试测试"/>
          </view>
        </template>
      </yl-custom-filter>
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

export default {
  components: {
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
      this.show = false;
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
