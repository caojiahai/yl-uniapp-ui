<template>
  <view class="content">
    <u-navbar
      :autoBack="true"
      title="个人中心"
    >
    </u-navbar>
    <u-icon name="chat"></u-icon>
    <DefaultCard>
      123123
    </DefaultCard>
  </view>
</template>

<script>
import DefaultCard from "../../components/DefaultCard.vue";

export default {
  components: {DefaultCard},
  data() {
    return {
      title: ''
    }
  },
  onLoad() {

  },
  methods: {}
}
</script>

<style>

</style>
