<template>
  <view className="home">
    <u-navbar :autoBack="true" title="列表展示"/>
    <view style="margin-top: 44px;padding: 24rpx;background-color: #f8f8f8;">
      <yl-default-card>
        <yl-default-list title="列表" value="222"/>
        <u-divider/>
        <yl-item-layout-list label="任务内容">
          <template #content>
            <view style="display: flex;align-items: center;margin-top: 8rpx;">
              <text>7.2w</text>
              <yl-tab-tag color="red" sub-title="费用" title="预估"/>
            </view>
          </template>
        </yl-item-layout-list>
        <u-divider/>
        <yl-item-list label="任务费用">
          <template #content>
            <view style="display: flex;align-items: center">
              <text>7.2w</text>
              <yl-tab-tag color="red" sub-title="费用" title="预估"/>
            </view>
          </template>
        </yl-item-list>
        <u-divider/>
        <yl-select-list :icon-name="'checkmark'" :selected="true" value="测试测试"/>
      </yl-default-card>
    </view>
  </view>
</template>
<script>
import YlDefaultCard from "@/components/card/yl-default-card.vue";
import YlDefaultList from "@/components/list/yl-default-list.vue";
import YlItemLayoutList from "@/components/list/yl-item-layout-list.vue";
import YlTabTag from "@/components/tag/yl-tab-tag.vue";
import YlItemList from "@/components/list/yl-item-list.vue";
import YlSelectList from "@/components/list/yl-select-list.vue";

export default {
  components: {
    YlSelectList,
    YlItemList,
    YlTabTag,
    YlItemLayoutList,
    YlDefaultList,
    YlDefaultCard
  },
  data() {
    return {}
  },
  methods: {}
}
</script>
<style scoped>
.home {
  height: 100vh;
  background-color: #f8f8f8;
}
</style>
