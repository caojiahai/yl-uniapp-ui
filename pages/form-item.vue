<template>
  <view className="home">
    <u-navbar :autoBack="true" title="表单子项"/>
    <view style="margin-top: 44px;padding: 24rpx;background-color: #f8f8f8;">
      <yl-default-card>
        <yl-form-item
          :required="true"
          default-value="222"
          justify-content="flex-end"
          title="测试"
          @itemClick="confirm"
        >
          <template #extend>
            <u-popup :show="show" closeOnClickOverlay mode="bottom" @close="show = false">
              11111
            </u-popup>
          </template>
        </yl-form-item>
        <u-divider/>
        <yl-form-item-input title="标题"/>
        <u-divider/>
        <yl-form-item-popup
          :popup-show="show1"
          :required="true"
          default-value=""
          justify-content="flex-end"
          title="测试标题"
          @closePopup="show1 = false"
          @showPopup="show1 = true"
        >
          <yl-default-header @leftClick="show1 = false" @rightClick="show1 = false"/>
          <yl-select-list :icon-name="'checkmark'" :selected="true" value="测试测试"/>
        </yl-form-item-popup>
      </yl-default-card>
    </view>
  </view>
</template>
<script>
import YlDefaultCard from "@/components/card/yl-default-card.vue";
import YlFormItem from "@/components/form-item/yl-form-item.vue";
import YlFormItemInput from "@/components/form-item/yl-form-item-input.vue";
import YlFormItemPopup from "@/components/form-item/yl-form-item-popup.vue";
import YlSelectList from "@/components/list/yl-select-list.vue";
import YlDefaultHeader from "@/components/header/yl-default-header.vue";

export default {
  components: {
    YlDefaultHeader, YlSelectList,
    YlFormItemPopup,
    YlFormItemInput,
    YlFormItem,
    YlDefaultCard
  },
  data() {
    return {
      show: false,
      show1: false
    }
  },
  methods: {
    confirm() {
      this.show = true;
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
