<template>
  <swiper class="my-swiper" :autoplay="5000" indicator-color="#c40000">
    <swiper-item v-for="(item, index) in list" :key="index">
      <image class="img" :src="item.carouselUrl" alt="" @click="goTo(item.redirectUrl)">
    </swiper-item>
  </swiper>
</template>

<script>
export default {
  props: {
    list: {
      type: Array,
      default: null
    }
  },
  methods: {
    goTo(url) {
      window.open(url)
    }
  }
}
</script>

<style lang='less' scoped>
 .swiper .swiper-item {
    image {
      width: 10%;
      height: 10%;
    }
  }
</style>
