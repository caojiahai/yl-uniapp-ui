<template>
  <view class="home">
    <u-navbar :autoBack="true" title="标签展示"/>
    <view style="margin-top: 44px;padding: 24rpx;background-color: #f8f8f8;">
      <yl-default-card>
        <yl-default-tag/>
        <u-divider/>
        <yl-tab-tag sub-title="值值值值值" title="标签"/>
        <u-divider/>
        <yl-tag :selected="false" title="标签"/>
        <u-divider/>
        <yl-tag :selected="true" title="标签"/>
      </yl-default-card>
    </view>
  </view>
</template>
<script>
import YlDefaultCard from "@/components/card/yl-default-card.vue";
import YlTag from "@/components/tag/yl-tag.vue";
import YlTabTag from "@/components/tag/yl-tab-tag.vue";
import YlDefaultTag from "@/components/tag/yl-default-tag.vue";

export default {
  components: {
    YlDefaultTag,
    YlTabTag,
    YlTag,
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
