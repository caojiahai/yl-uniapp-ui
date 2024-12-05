<template>
  <view className="home">
    <u-navbar :autoBack="true" title="过滤"/>
    <view style="margin-top: 44px;padding: 24rpx;background-color: #f8f8f8;">
      <yl-default-card>
        <yl-custom-select-filter
          :item-list="[{ id: 1, name: '111'}, { id: 2, name: '222'}]"
          :show="show"
          key-name="name"
          @cancel="cancel"
          @close="show = false"
          @confirm="confirm"
        >
          <template #content>
            <view @click="show = true">自定义Select弹窗</view>
          </template>
        </yl-custom-select-filter>
        <u-divider/>
        <yl-custom-popup-filter :popup-round="20" :show="show1" @close="show1 = false">
          <template #content>
            <view @click="show1 = true">自定义Popup弹窗</view>
          </template>
          <template #popup>
            <view @click="show1 = false">
              222
            </view>
          </template>
        </yl-custom-popup-filter>
        <u-divider/>
        <yl-popup-filter :show="show3">
          <template #content>
            <view @click="show3 = true">全屏弹出</view>
          </template>
          <template #popup>
            <view @click="show3 = false">全屏弹出</view>
          </template>
        </yl-popup-filter>
        <u-divider/>
        <yl-select-filter :itemList="itemList"></yl-select-filter>
        <u-divider/>
        <yl-sort-filter/>
      </yl-default-card>
    </view>
    <u-divider/>
    <yl-custom-filter :bg-height="182" :popup-round="20" :show="show2" @close="show2 = false">
      <template #content>
        <view style="display: flex;align-items: center;justify-content: space-between;">
          <view @click="show2 = true">自定义弹出，根据外围宽度弹出</view>
        </view>
      </template>
      <template #popup>
        <view>
          <yl-select-list :icon-name="'checkmark'" :selected="true" value="测试测试"/>
        </view>
      </template>
    </yl-custom-filter>
  </view>
</template>
<script>
import YlDefaultCard from "@/components/card/yl-default-card.vue";
import YlPopupFilter from "@/components/filter/yl-popup-filter.vue";
import YlCustomSelectFilter from "@/components/filter/yl-custom-select-filter.vue";
import YlCustomPopupFilter from "@/components/filter/yl-custom-popup-filter.vue";
import YlCustomFilter from "@/components/filter/yl-custom-filter.vue";
import YlSelectList from "@/components/list/yl-select-list.vue";
import YlSelectFilter from "@/components/filter/yl-select-filter.vue";
import YlSortFilter from "@/components/filter/yl-sort-filter.vue";

export default {
  components: {
    YlSortFilter,
    YlSelectFilter,
    YlSelectList,
    YlCustomFilter,
    YlCustomPopupFilter,
    YlCustomSelectFilter,
    YlPopupFilter,
    YlDefaultCard
  },
  data() {
    return {
      show: false,
      show1: false,
      show2: false,
      show3: false,
      show4: false,
      show5: false,
      itemList: [{label: '全部订单', id: ''}]
    }
  },
  methods: {
    cancel() {
      this.show = false;
    },
    confirm() {
      this.show = false;
    }
  }
}
</script>
<style scoped>
.home {
  height: 100vh;
  background-color: #f8f8f8;
}
</style>
