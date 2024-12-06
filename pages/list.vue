<template>
  <view className="home">
    <u-navbar :autoBack="true" title="列表"/>
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
        <u-divider :margin="0"/>
        <yl-item-list label="任务附件">
          <template #content>
            <yl-ellipsis
              :suffix-count="5"
              color="#ff9438"
              size="30rpx"
              text="我是标题我是标题我是标题我是标题我是标题我是标题我是标题.pdf"
            />
            <view style="width: 20px; margin-left: 10px;">
              <u-icon color="#ff9438" name="arrow-right" size="14"/>
            </view>
          </template>
        </yl-item-list>
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
import YlEllipsis from "@/components/ellipsis/yl-ellipsis.vue";

export default {
  components: {
    YlEllipsis,
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
