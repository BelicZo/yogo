<template>
<div>
  <van-swipe :autoplay="3000" @change="onSwipeChange" :height="129.38">
    <van-swipe-item v-for="(image, index) in images" :key="index" @click='clickSwipeItem'>
      <img class="swipe-img" v-lazy="image" />
    </van-swipe-item>
  </van-swipe>

  <van-swipe :height="200">
    <van-swipe-item>
      <van-row gutter="35">
        <van-col span="6" v-for="(icon, index) in icons" :key="index">
          <van-icon name="wap-nav" size="5em"></van-icon>
        </van-col>
      </van-row>
    </van-swipe-item>
  </van-swipe>

  <!-- <router-view></router-view> -->
</div>
</template>

<script>
// import HomeSwiper from './components/swiper'
import { Swipe, SwipeItem, Icon, Col, Row } from 'vant'
export default {
  name: 'home',
  data () {
    return {
      icons: [1, 2, 3, 4, 5, 2, 3, 4],
      images: [
        'http://img1.qunarzz.com/piao/fusion/1801/1a/94428c6dea109402.jpg_640x200_2cf590d8.jpg',
        'http://img1.qunarzz.com/piao/fusion/1802/42/7c92b9a381e46402.jpg_640x200_1cdce2a4.jpg',
        'http://img1.qunarzz.com/piao/fusion/1802/51/e78f936a5b404102.jpg_640x200_c14f0b3a.jpg',
        'http://img1.qunarzz.com/piao/fusion/1712/91/a275569091681d02.jpg_640x200_0519ccb9.jpg'
      ]
    }
  },
  computed: {
    swipeRow: () => {
      return parseInt(this.icons / 2)
    }
  },
  components: {
    'van-swipe': Swipe,
    'van-swipe-item': SwipeItem,
    'van-icon': Icon,
    'van-col': Col,
    'van-row': Row
  },
  methods: {
    onSwipeChange (index) {
      // console.log('当前索引: ' + index)
    },
    clickSwipeItem (a, b) {
      console.log('点击swipe item', a)
    }
  }
}
</script>

<style lang='stylus' scoped>
.swipe-img 
  width 100%
</style>
