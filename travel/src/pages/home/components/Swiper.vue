<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if="showSwiper">
      <swiper-slide v-for="item of list" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" />
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: "HomeSwiper",
  props: {
    list:Array
  },
  data() {
    return {
      swiperOption: {
        pagination: ".swiper-pagination",
        loop :true
      }
     
    };
  },
  computed : {
      showSwiper () {
        return this.list.length
      }
  }
};
</script>

<style lang='stylus' scoped>
.wrapper >>> .swiper-pagination-bullet-active
  background: #fff
.wrapper
  width: 100%
  overflow: hidden
  height: 0
  padding-bottom: 26.5700483%
  background: #eee
  .swiper-img
    width: 100%
</style>

